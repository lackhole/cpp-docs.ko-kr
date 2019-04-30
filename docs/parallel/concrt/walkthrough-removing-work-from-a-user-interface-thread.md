---
title: '연습: 사용자 인터페이스 스레드에서 작업 제거'
ms.date: 11/19/2018
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
ms.openlocfilehash: 1838ad0d6adb146adacb8b3a395f44f76e2a8d3f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407814"
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>연습: 사용자 인터페이스 스레드에서 작업 제거

이 문서에는 작업자 스레드를 Microsoft Foundation 클래스 (MFC) 응용 프로그램의 사용자 인터페이스 (UI) 스레드에서 수행 되는 작업을 이동할 동시성 런타임을 사용 하는 방법을 보여 줍니다. 이 문서에는 긴 그리기 작업의 성능을 향상 하는 방법을 보여 줍니다.

차단 작업을 오프 로드 하 여 UI 스레드에서 작업 제거 예를 들어 작업자 스레드에 드로잉을 향상 시킬 수 응용 프로그램의 응답성. 이 연습에서는 긴 차단 작업을 보여 주기 위해 Mandelbrot 프랙탈을 생성 하는 그리기 루틴을 사용 하 합니다. Mandelbrot 프랙탈 차세대 각 픽셀의 계산이 다른 모든 계산은 독립적 이므로 병렬화에 대 한 좋은 후보 이기도 합니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 시작 하기 전에 다음 항목을 읽어보세요.

- [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)

- [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)

- [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)

- [PPL에서의 취소](cancellation-in-the-ppl.md)

이 연습을 시작 하기 전에 MFC 응용 프로그램 개발 및 GDI +의 기본을 이해 하는 것이 좋습니다. MFC에 대 한 자세한 내용은 참조 하세요. [MFC Desktop Applications](../../mfc/mfc-desktop-applications.md)합니다. GDI +에 대 한 자세한 내용은 참조 하세요. [GDI +](https://msdn.microsoft.com/library/windows/desktop/ms533798)합니다.

##  <a name="top"></a> 섹션

이 연습에는 다음과 같은 섹션이 있습니다.

- [MFC 응용 프로그램 만들기](#application)

- [직렬 버전 Mandelbrot 응용 프로그램의 구현](#serial)

- [사용자 인터페이스 스레드에서 작업 제거](#removing-work)

- [그리기 성능 향상](#performance)

- [취소에 대 한 지원 추가](#cancellation)

##  <a name="application"></a> MFC 응용 프로그램 만들기

이 섹션에는 기본 MFC 응용 프로그램을 만드는 방법을 설명 합니다.

### <a name="to-create-a-visual-c-mfc-application"></a>시각적 개체를 만들려면 C++ MFC 응용 프로그램

1. **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.

1. 에 **새 프로젝트** 대화 상자의 **설치 된 템플릿** 창 **Visual C++** 를 선택한 다음를 **템플릿** 창 선택 **MFC 응용 프로그램**합니다. 예를 들어, 프로젝트 이름을 입력 `Mandelbrot`를 클릭 하 고 **확인** 표시할 합니다 **MFC 응용 프로그램 마법사**합니다.

1. 에 **응용 프로그램 종류** 창 **단일 문서**합니다. 있는지 확인 합니다 **문서/뷰 아키텍처 지원** 확인란의 선택을 취소 합니다.

1. 클릭 **완료** 프로젝트를 만들고 닫습니다 합니다 **MFC 응용 프로그램 마법사**합니다.

   응용 프로그램을 빌드하고 실행 하 여 만들어졌는지 확인 합니다. 응용 프로그램을 작성 하는 **빌드** 메뉴에서 클릭 **솔루션 빌드**합니다. 응용 프로그램이 성공적으로 빌드되면 클릭 하 여 응용 프로그램 실행 **디버깅 시작** 에 **디버그** 메뉴.

##  <a name="serial"></a> 직렬 버전 Mandelbrot 응용 프로그램의 구현

이 섹션에는 Mandelbrot 프랙탈을 그리는 방법을 설명 합니다. 이 버전을 GDI + Mandelbrot 프랙탈을 그리는 [비트맵](/windows/desktop/api/gdiplusheaders/nl-gdiplusheaders-bitmap) 개체 및 해당 비트맵의 내용을 클라이언트 창에 복사 합니다.

#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>Mandelbrot 응용 프로그램의 직렬 버전을 구현 하려면

1. Stdafx.h에서 다음 추가 `#include` 지시문:

   [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]

1. ChildView.h에서 후 합니다 `pragma` 지시문을 정의 합니다 `BitmapPtr` 형식. 합니다 `BitmapPtr` 형식에 대 한 포인터를 사용 하면를 `Bitmap` 여러 구성 요소에서 공유 하는 개체입니다. `Bitmap` 모든 구성 요소에서 참조 되지 않는 개체가 삭제 됩니다.

   [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]

1. ChildView.h, 다음 코드를 추가 합니다 `protected` 부분을 `CChildView` 클래스:

   [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]

1. ChildView.cpp, 주석 처리 하거나 다음 줄을 제거 합니다.

   [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]

   디버그 빌드에서이 단계에서 사용 하 여 응용 프로그램을 방지 합니다 `DEBUG_NEW` 할당자에 GDI +와 호환 되지 않습니다.

1. ChildView.cpp, 추가 된 `using` 지시문을 `Gdiplus` 네임 스페이스.

   [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]

1. 생성자 및 소멸자의 다음 코드를 추가 합니다 `CChildView` 클래스를 초기화 한 GDI +를 종료 합니다.

   [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]

1. `CChildView::DrawMandelbrot` 메서드를 구현합니다. 이 메서드는 지정 된 Mandelbrot 프랙탈을 그리는 데 `Bitmap` 개체입니다.

   [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]

1. `CChildView::OnPaint` 메서드를 구현합니다. 이 메서드를 호출 `CChildView::DrawMandelbrot` 의 내용을 복사는 `Bitmap` 창에는 개체입니다.

   [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]

1. 응용 프로그램을 빌드하고 실행 하 여 성공적으로 업데이트 되었는지 확인 합니다.

다음 그림에서는 Mandelbrot 응용 프로그램의 결과 보여 줍니다.

![Mandelbrot 응용 프로그램](../../parallel/concrt/media/mandelbrot.png "Mandelbrot 응용 프로그램")

각 픽셀에 대 한 계산 과정이 이기 때문에 UI 스레드 전체 계산이 완료 될 때까지 추가 메시지를 처리할 수 없습니다. 이 응용 프로그램의 응답성을 저하 될 수 있습니다. 그러나 UI 스레드에서 작업을 제거 하 여이 문제를 덜 수 있습니다.

[[맨 위로 이동](#top)]

##  <a name="removing-work"></a> UI 스레드에서 작업 제거

이 섹션에는 Mandelbrot 응용 프로그램의 UI 스레드에서 그리기 작업을 제거 하는 방법을 보여 줍니다. 그리기 작업을 UI 스레드에서 작업자 스레드를 이동 하 여 UI 스레드에서 작업자 스레드는 백그라운드에서 이미지를 생성 합니다. 메시지를 처리할 수 있습니다.

동시성 런타임에서 작업을 실행 하려면 세 가지 방법으로 제공 합니다. [작업 그룹](../../parallel/concrt/task-parallelism-concurrency-runtime.md), [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md), 및 [간단한 작업](../../parallel/concrt/task-scheduler-concurrency-runtime.md)합니다. 이 예제에서는 이러한 메커니즘 중 하나를 사용 하 여 UI 스레드에서 작업을 제거할 수 있습니다, 있지만 [concurrency:: task_group](reference/task-group-class.md) 작업 그룹이 취소를 지원 하기 때문에 개체입니다. 이 연습에서는 나중에 클라이언트 창 크기를 조정할 때 수행 되는 작업의 양을 줄일 수 및 창을 소멸 될 때 정리를 수행 하려면 취소를 사용 합니다.

또한이 예제에서는 한 [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) 개체를 사용 하 여 UI 스레드와 작업자 스레드가 서로 통신할 수 있습니다. 에 대 한 포인터를 이미지를 생성 하는 작업자 스레드 후 보냅니다를 `Bitmap` 개체를 `unbounded_buffer` 개체 및 UI 스레드로 그리기 메시지를 게시 합니다. UI 스레드는 다음에서 수신 합니다 `unbounded_buffer` 개체는 `Bitmap` 개체 및 클라이언트 창으로 그립니다.

#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>UI 스레드에서 그리기 작업을 제거 하려면

1. Stdafx.h에서 다음 추가 `#include` 지시문:

   [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]

1. ChildView.h, 추가 `task_group` 및 `unbounded_buffer` 멤버 변수를 `protected` 섹션을 `CChildView` 클래스. 합니다 `task_group` 개체는; 그리기를 수행 하는 작업을 보유 합니다 `unbounded_buffer` 완료 Mandelbrot 이미지를 보유 하는 개체입니다.

   [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]

1. ChildView.cpp, 추가 된 `using` 지시문을 `concurrency` 네임 스페이스.

   [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]

1. 에 `CChildView::DrawMandelbrot` 메서드를 호출한 후 `Bitmap::UnlockBits`, 호출를 [concurrency:: send](reference/concurrency-namespace-functions.md#send) 전달할 함수를 `Bitmap` UI 스레드로 개체입니다. 그런 다음 UI 스레드로 그리기 메시지를 게시 하 고 클라이언트 영역을 무효화 합니다.

   [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]

1. 업데이트를 `CChildView::OnPaint` 업데이트를 수신 하는 방법 `Bitmap` 개체 및 클라이언트 창에는 이미지를 그립니다.

   [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]

   `CChildView::OnPaint` 메서드는 메시지 버퍼에 존재 하지 않는 경우 Mandelbrot 이미지를 생성 하는 작업을 만듭니다. 메시지 버퍼에 포함 되지 않습니다는 `Bitmap` 예: 초기 그리기 메시지를 클라이언트 창 앞에 다른 창이 이동 하는 경우에서 개체입니다.

1. 응용 프로그램을 빌드하고 실행 하 여 성공적으로 업데이트 되었는지 확인 합니다.

그리기 작업을 백그라운드에서 수행 되기 때문에 UI 응답성이 향상 되었습니다.

[[맨 위로 이동](#top)]

##  <a name="performance"></a> 그리기 성능 향상

다른 모든 계산은 각 픽셀의 계산이 무관 Mandelbrot 프랙탈의 생성은 병렬 처리에 적합 합니다. 그리기 프로시저를 병렬화 하 여 외부 변환 `for` 루프를 `CChildView::DrawMandelbrot` 메서드를 호출 하는 [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) 알고리즘을 다음과 같이 합니다.

[!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]

각 비트맵 요소의 계산 독립적 이므로 비트맵 메모리에 액세스 하는 그리기 작업을 동기화 할 필요가 없습니다. 이 통해 사용 가능한 프로세서 증가 수와 크기를 조정 하는 성능.

[[맨 위로 이동](#top)]

##  <a name="cancellation"></a> 취소에 대 한 지원 추가

이 섹션에는 창 크기 조정을 처리 하는 방법 및 창을 소멸 될 때 모든 활성 그리기 작업을 취소 하는 방법을 설명 합니다.

문서 [PPL에서의 취소](cancellation-in-the-ppl.md) 런타임에서에서 취소가 작동 하는 방법에 대해 설명 합니다. 취소는 협조적입니다. 따라서 즉시 발생 하지 않습니다. 취소 된 작업을 중지 하려면 런타임에서는 런타임에 태스크에서 후속 호출 하는 동안 내부 예외가 throw 됩니다. 이전 섹션에 사용 하는 방법을 보여 줍니다는 `parallel_for` 그리기 작업의 성능을 향상 하는 알고리즘입니다. 에 대 한 호출 `parallel_for` 작업을 중지 하도록 런타임에 있으며 따라서 다음 작업을 취소 합니다.

### <a name="cancelling-active-tasks"></a>활성 작업 취소

Mandelbrot 응용 프로그램을 만듭니다 `Bitmap` 클라이언트 창의 크기와 일치 하는 개체입니다. 클라이언트 창 크기를 조정할 때마다 응용 프로그램에는 새 창 크기에 대 한 이미지를 생성할지 추가 백그라운드 작업을 만듭니다. 응용 프로그램에는 이러한 중간 이미지; 않아도 최종 창 크기를 이미지에만 필요합니다. 를 방지 하기 위해이 추가 작업을 수행할 수 없도록 응용 프로그램에 대 한 메시지 처리기에서 모든 활성 그리기 작업을 취소할 수 있습니다 합니다 `WM_SIZE` 및 `WM_SIZING` 메시지 및 다음 일정을 조정 그리기 창의 크기를 조정할 한 후에 작동 합니다.

응용 프로그램 크기를 창 크기를 조정할 때 활성 그리기 작업을 취소 하려면 호출을 [concurrency::task_group::cancel](reference/task-group-class.md#cancel) 에 대 한 처리기에서 메서드는 `WM_SIZING` 및 `WM_SIZE` 메시지입니다. 에 대 한 처리기를 `WM_SIZE` 호출도 메시지를 [concurrency::task_group::wait](reference/task-group-class.md#wait) 모든 활성 작업이 완료 되 고 다음 업데이트 된 창 크기에 대 한 그리기 작업 다시 예약을 대기 하는 방법입니다.

클라이언트 창이 소멸 될 때 모든 활성 그리기 작업을 취소 하는 것이 좋습니다. 모든 활성 그리기 작업을 취소 하면 작업자 스레드 클라이언트 창이 소멸 된 후 메시지 UI 스레드를 게시 하지 마십시오. 응용 프로그램에 대 한 처리기에서 모든 활성 그리기 작업을 취소 합니다 `WM_DESTROY` 메시지입니다.

### <a name="responding-to-cancellation"></a>취소에 응답

`CChildView::DrawMandelbrot` 그리기 작업을 수행 하는 메서드에 취소에 응답 해야 합니다. 런타임에서 예외 처리 작업을 취소 하기 때문에 `CChildView::DrawMandelbrot` 메서드는 모든 리소스가 올바르게 정리 되도록 예외 로부터 안전한 메커니즘을 사용 해야 합니다. 이 예제에서는 합니다 *Resource Acquisition Is Initialization* (RAII) 패턴 비트맵 비트는 잠긴 작업이 취소 되 면 되도록 합니다.

##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>Mandelbrot 응용 프로그램에서 취소에 대 한 지원을 추가 하려면

1. ChildView.h에서를 `protected` 의 섹션을 `CChildView` 클래스에 대 한 선언을 추가 합니다 `OnSize`, `OnSizing`, 및 `OnDestroy` 메시지 맵 함수.

   [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]

1. ChildView.cpp에 대 한 처리기를 포함 하는 메시지 맵을 수정 합니다 `WM_SIZE`, `WM_SIZING`, 및 `WM_DESTROY` 메시지입니다.

   [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]

1. `CChildView::OnSizing` 메서드를 구현합니다. 이 메서드는 기존의 모든 그리기 작업을 취소합니다.

   [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]

1. `CChildView::OnSize` 메서드를 구현합니다. 이 메서드는 기존의 모든 그리기 작업을 취소 하 고 업데이트 된 클라이언트 창 크기에 대 한 새 그리기 작업을 만듭니다.

   [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]

1. `CChildView::OnDestroy` 메서드를 구현합니다. 이 메서드는 기존의 모든 그리기 작업을 취소합니다.

   [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]

1. ChildView.cpp, 정의 된 `scope_guard` RAII 패턴을 구현 하는 클래스입니다.

   [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]

1. 다음 코드를 추가 합니다 `CChildView::DrawMandelbrot` 메서드를 호출한 후 `Bitmap::LockBits`:

   [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]

   이 코드는 만들어 취소를 처리 한 `scope_guard` 개체입니다. 개체가 범위를 벗어나면 비트맵 bits 잠금을 해제 합니다.

1. 끝을 수정 합니다 `CChildView::DrawMandelbrot` 해제 하는 방법의 `scope_guard` 비트맵 비트 잠긴 후 하지만 UI 스레드에서 모든 메시지가 전송 되기 전에 개체. 이렇게 하면 UI 스레드가 비트맵 비트 잠금이 해제 된 전에 업데이트 되지 않습니다.

   [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]

9. 응용 프로그램을 빌드하고 실행 하 여 성공적으로 업데이트 되었는지 확인 합니다.

창 크기를 조정 하면 드로잉 작업 최종 창 크기에 대해서만 수행 됩니다. 모든 활성 그리기 작업 창이 소멸 되는 경우에 취소 됩니다.

[[맨 위로 이동](#top)]

## <a name="see-also"></a>참고자료

[동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)<br/>
[병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)<br/>
[PPL에서의 취소](cancellation-in-the-ppl.md)<br/>
[MFC 데스크톱 응용 프로그램](../../mfc/mfc-desktop-applications.md)
