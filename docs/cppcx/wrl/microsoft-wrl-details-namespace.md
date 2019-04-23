---
title: Microsoft::WRL::Details 네임스페이스
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
ms.openlocfilehash: fce6e620600164e73d3708d98d8a7fa979e8ab42
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027482"
---
# <a name="microsoftwrldetails-namespace"></a>Microsoft::WRL::Details 네임스페이스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
namespace Microsoft::WRL::Details;
```

## <a name="members"></a>멤버

### <a name="classes"></a>클래스

|이름|설명|
|----------|-----------------|
|[ComPtrRef 클래스](comptrref-class.md)|ComPtr 형식의 개체에 대 한 참조를 나타내는\<T >입니다.|
|[ComPtrRefBase 클래스](comptrrefbase-class.md)|에 대 한 기본 클래스를 나타냅니다 합니다 [ComPtrRef](comptrref-class.md) 클래스입니다.|
|[DontUseNewUseMake 클래스](dontusenewusemake-class.md)|연산자를 사용 하는 것을 금지 `new` 에서 `RuntimeClass`합니다. 결과적으로 사용 해야 합니다 [함수](make-function.md) 대신 합니다.|
|[EventTargetArray 클래스](eventtargetarray-class.md)|이벤트 처리기의 배열을 나타냅니다.|
|[MakeAllocator 클래스](makeallocator-class.md)|약한 참조 지원을 유무는 활성화 가능한 클래스에 대 한 메모리를 할당합니다.|
|[ModuleBase 클래스](modulebase-class.md)|기본 클래스를 나타냅니다 합니다 [모듈](module-class.md) 클래스입니다.|
|[RemoveIUnknown 클래스](removeiunknown-class.md)|해당 하는 형식을 만들 수는 `IUnknown`-기반, 하지만 형식은 비가상 `QueryInterface`를 `AddRef`, 및 `Release` 메서드.|
|[WeakReference 클래스](weakreference-class.md)|나타냅니다는 *약한 참조* Windows 런타임 또는 클래식 COM.를 사용 하 여 사용할 수 있는 약한 참조는 액세스할 수 있거나 액세스할 수 없는 개체를 나타냅니다.|

### <a name="structures"></a>구조체

|이름|설명|
|----------|-----------------|
|[ArgTraits 구조체](argtraits-structure.md)|인터페이스 및 지정 된 개수의 매개 변수를 가진 익명 멤버 함수는 지정 된 대리자를 선언 합니다.|
|[ArgTraitsHelper 구조체](argtraitshelper-structure.md)|대리자 인수의 공통 된 특징을 정의할 수 있습니다.|
|[BoolStruct 구조체](boolstruct-structure.md)|정의 여부는 `ComPtr` 인터페이스의 개체 수명을 관리 하는 합니다. `BoolStruct` 내부적으로 사용 되는 [BoolType()](comptr-class.md#operator-microsoft-wrl-details-booltype) 연산자입니다.|
|[CreatorMap 구조체](creatormap-structure.md)|초기화, 등록 및 개체의 등록을 취소 하는 방법에 대 한 정보를 포함 합니다.|
|[DerefHelper 구조체](derefhelper-structure.md)|에 대 한 역참조 포인터를 나타내는 `T*` 템플릿 매개 변수입니다.|
|[EnableIf 구조체](enableif-structure.md)|첫 번째 템플릿 매개 변수를 평가 하는 경우 두 번째 템플릿 매개 변수로 지정 된 형식의 데이터 멤버를 정의 `true`합니다.|
|[FactoryCache 구조체](factorycache-structure.md)|클래스 팩터리 및 등록된 된 Windows 런타임 또는 COM 클래스 개체를 식별 하는 값의 위치를 포함 합니다.|
|[ImplementsBase 구조체](implementsbase-structure.md)|템플릿 매개 변수 형식의 유효성을 검사 하는 데 [Implements 구조체](implements-structure.md)합니다.|
|[ImplementsHelper 구조체](implementshelper-structure.md)|구현에 유용한 합니다 [구현](implements-structure.md) 구조입니다.|
|[InterfaceList 구조체](interfacelist-structure.md)|인터페이스의 재귀 목록을 만드는 데 사용 합니다.|
|[InterfaceListHelper 구조체](interfacelisthelper-structure.md)|빌드는 `InterfaceList` 재귀적으로 지정 된 템플릿 매개 변수 인수를 적용 하 여 형식입니다.|
|[InterfaceTraits 구조체](interfacetraits-structure.md)|인터페이스의 공통 특성을 구현 합니다.|
|[InvokeHelper 구조체](invokehelper-structure.md)|구현을 제공 합니다 `Invoke()` 메서드 인수 형식 및 지정 된 수에 따라 합니다.|
|[IsBaseOfStrict 구조체](isbaseofstrict-structure.md)|형식 하나가 다른 형식의 기본 형식인지 테스트합니다.|
|[IsSame 구조체](issame-structure.md)|형식이 지정 된 것과 같습니다 다른 테스트 형식을 지정 합니다.|
|[Nil 구조체](nil-structure.md)|지정 되지 않은 (선택 사항) 템플릿 매개 변수를 나타내는 데 사용 합니다.|
|[RemoveReference 구조체](removereference-structure.md)|지정 된 클래스 템플릿 매개 변수에서 참조 또는 rvalue 참조 특성을 제거합니다.|
|[RuntimeClassBase 구조체](runtimeclassbase-structure.md)|검색 하는 데 `RuntimeClass` 에 [확인](make-function.md) 함수입니다.|
|[RuntimeClassBaseT 구조체](runtimeclassbaset-structure.md)|도우미 메서드를 제공 `QueryInterface` 작업과 인터페이스 Id를 시작 합니다.|
|[VerifyInheritanceHelper 구조체](verifyinheritancehelper-structure.md)|하나의 인터페이스는 다른 인터페이스에서 파생 됩니다 있는지 테스트 합니다.|
|[VerifyInterfaceHelper 구조체](verifyinterfacehelper-structure.md)|템플릿 매개 변수로 지정 된 인터페이스에 특정 요구 사항을 충족 하는지 확인 합니다.|

### <a name="enumerations"></a>열거형

|이름|설명|
|----------|-----------------|
|[AsyncStatusInternal 열거형](asyncstatusinternal-enumeration.md)|비동기 작업의 상태 내부 열거형 사이 매핑을 지정 및 `Windows::Foundation::AsyncStatus` 열거형입니다.|

### <a name="functions"></a>함수

|이름|설명|
|----------|-----------------|
|[ActivationFactoryCallback 함수](activationfactorycallback-function.md)|지정 된 활성화 ID에 대 한 활성화 팩터리를 가져옵니다.|
|[Move 함수](move-function.md)|다른 곳에서 지정 된 인수를 이동합니다.|
|[RaiseException 함수](raiseexception-function.md)|호출 스레드에서 예외가 발생 합니다.|
|[Swap 함수(WRL)](swap-function-wrl.md)|두 개의 지정 된 인수 값을 교환 합니다.|
|[TerminateMap 함수](terminatemap-function.md)|지정된 된 모듈의 클래스 팩터리를 종료합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="see-also"></a>참고자료

[Microsoft::WRL 네임스페이스](microsoft-wrl-namespace.md)<br/>
[Microsoft::WRL::Wrappers 네임스페이스](microsoft-wrl-wrappers-namespace.md)