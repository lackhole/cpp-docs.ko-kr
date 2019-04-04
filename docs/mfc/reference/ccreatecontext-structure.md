---
title: CCreateContext 구조체
ms.date: 11/04/2016
f1_keywords:
- CCreateContext
helpviewer_keywords:
- CCreateContext structure [MFC]
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
ms.openlocfilehash: 795b20cba41eeca8cc1a32e312edf065b718f364
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768488"
---
# <a name="ccreatecontext-structure"></a>CCreateContext 구조체

프레임 워크를 사용 하는 `CCreateContext` 프레임 창 및 문서와 연결 된 뷰를 만들 때 구성 합니다.

## <a name="syntax"></a>구문

```
struct CCreateContext
```

## <a name="remarks"></a>설명

`CCreateContext` 구조 이며 기본 클래스를 포함 하지 않습니다.

창을 만든 경우이 구조에 있는 값 데이터 보기로 문서의 구성 요소를 연결 하는 데 사용 하는 정보를 제공 합니다. 사용 해야 `CCreateContext` 생성 프로세스의 파트를 재정의 하는 경우.

`CCreateContext` 구조 문서, 프레임 창, 보기 및 문서 서식 파일에 대 한 포인터를 포함 합니다. 에 대 한 포인터도 포함 된 `CRuntimeClass` 만드는 뷰의 유형을 식별 하는 합니다. 런타임 클래스 정보 및 현재 문서 포인터를 동적으로 새 뷰를 만드는 사용 됩니다. 다음 표에서 방법과 시기를 제안 각 `CCreateContext` 멤버를 사용할 수 있습니다.

|멤버|형식|에 대 한 것|
|------------|----------|--------------------|
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass` 뷰의 새 만듭니다.|
|`m_pCurrentDoc`|`CDocument*`|기존 문서를 새 보기를 사용 하 여 연결 합니다.|
|`m_pNewDocTemplate`|`CDocTemplate*`|새 MDI 프레임 창 만들기와 연결 된 문서 템플릿.|
|`m_pLastView`|`CView*`|추가 뷰는 모델링 분할자 창 뷰 만들기 또는 문서에 대 한 두 번째 뷰 만들기와 같이 원래 뷰.|
|`m_pCurrentFrame`|`CFrameWnd*`|추가 프레임 창 모델링 됩니다, 문서에서 두 번째 프레임 창 만들기와 같이 프레임 창입니다.|

저장 된 정보는 문서 템플릿을 문서 및 관련된 구성 요소를 만들 때 유효성을 검사 합니다 `CCreateContext` 구조입니다. 예를 들어 뷰를 만들지는 존재 하지 않는 문서에 대 한 합니다.

> [!NOTE]
>  포인터의 모든 `CCreateContext` 는 선택 사항이 며 수 `NULL` 지정 되지 않은 또는 알 수 없는 경우.

`CCreateContext` 아래에 나열 된 멤버 함수에서 사용 하는 "를 참조 하십시오." 재정의 하려는 경우 특정 정보에 대 한 설명은 이러한 함수를 참조 하세요.

몇 가지 일반적인 지침은 다음과 같습니다.

- 와 같이 창 만들기에 대 한 인수로 전달 될 때 `CWnd::Create`, `CFrameWnd::Create`, 및 `CFrameWnd::LoadFrame`, 만들기 컨텍스트 지정 어떤 새 창에 연결 되어야 합니다. 대부분의 windows에 대 한 전체 구조는 선택 사항으로 `NULL` 포인터를 전달할 수 있습니다.

- 재정의 가능한 멤버 함수에 대 한 같은 `CFrameWnd::OnCreateClient`, `CCreateContext` 인수는 선택 사항입니다.

- 관련 된 멤버 함수에 대 한 보기를 만드는 정보를 제공 해야 충분 한 뷰를 만들려면. 예를 들어 분할 창에서 첫 번째 보기의 경우 클래스 정보 보기 및 현재 문서를 제공 해야 합니다.

일반적으로 프레임 워크 기본값을 사용 하는 경우 무시 해도 `CCreateContext`합니다. 고급 수정, Microsoft Foundation Class 라이브러리 소스 코드 또는 VIEWEX와 같은 샘플 프로그램에 사용 하려는 경우를 안내 합니다. 필수 매개 변수를 잊은 경우 framework 어설션이 알려줍니다 있습니다 하지 않았습니다.

에 대 한 자세한 `CCreateContext`, MFC 샘플을 참조 하세요 [VIEWEX](../../overview/visual-cpp-samples.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxext.h

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create)<br/>
[CFrameWnd::LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)<br/>
[CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)<br/>
[CSplitterWnd::Create](../../mfc/reference/csplitterwnd-class.md#create)<br/>
[CSplitterWnd::CreateView](../../mfc/reference/csplitterwnd-class.md#createview)<br/>
[CWnd::Create](../../mfc/reference/cwnd-class.md#create)
