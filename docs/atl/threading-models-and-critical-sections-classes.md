---
title: 스레딩 모델 및 임계 영역 클래스 (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, critical sections
- ATL, multithreading
- threading [ATL], models
- critical sections
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
ms.openlocfilehash: 98db15a1fee2637b9493b538468fa9446015404f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808159"
---
# <a name="threading-models-and-critical-sections-classes"></a>스레딩 모델 및 임계 영역 클래스

다음 클래스 정의 스레딩 모델 및 임계 영역:

- [CAtlAutoThreadModule](../atl/reference/catlautothreadmodule-class.md) 스레드 풀링, 아파트 모델 COM 서버를 구현 합니다.

- [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md) 스레드 풀링, 아파트 모델 COM 서버 구현에 대 한 메서드를 제공 합니다.

- [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) 변수 증가 및 감소 스레드로부터 안전한 메서드를 제공 합니다. 임계 영역을 제공합니다.

- [CComMultiThreadModelNoCS](../atl/reference/ccommultithreadmodelnocs-class.md) 변수 증가 및 감소 스레드로부터 안전한 메서드를 제공 합니다. 임계 영역을 제공 하지 않습니다.

- [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) 변수 증가 및 감소에 대 한 메서드를 제공 합니다. 임계 영역을 제공 하지 않습니다.

- [CComObjectThreadModel](../atl/reference/atl-typedefs.md#ccomobjectthreadmodel) 단일 개체 클래스에 대 한 적절 한 스레딩 모델 클래스를 결정 합니다.

- [CComGlobalsThreadModel](../atl/reference/atl-typedefs.md#ccomglobalsthreadmodel) 전역적으로 사용할 수 있는 개체에 대 한 적절 한 스레딩 모델 클래스를 결정 합니다.

- [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md) 가져오기 및 해제는 임계 영역에 대 한 메서드가 포함 되어 있습니다. 중요 섹션은 자동으로 초기화 됩니다.

- [CComCriticalSection](../atl/reference/ccomcriticalsection-class.md) 가져오기 및 해제는 임계 영역에 대 한 메서드가 포함 되어 있습니다. 중요 섹션을 명시적으로 초기화 되어야 합니다.

- [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) 의 메서드를 미러링 `CComCriticalSection` 임계 영역을 제공 하지 않고 있습니다. 메서드에서 `CComFakeCriticalSection` 아무 작업도 수행 합니다.

- [CRTThreadTraits](../atl/reference/crtthreadtraits-class.md) CRT 스레드에 대 한 생성 함수를 제공 합니다. 스레드 CRT 함수를 사용 하면이 클래스를 사용 합니다.

- [Win32ThreadTraits](../atl/reference/win32threadtraits-class.md) Windows 스레드 생성 기능을 제공 합니다. 스레드 CRT 함수를 사용 하지 않는 경우이 클래스를 사용 합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../atl/atl-class-overview.md)
