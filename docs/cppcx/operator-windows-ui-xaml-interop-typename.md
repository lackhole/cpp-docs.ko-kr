---
title: 연산자 Windows::UI::Xaml::Interop::TypeName
ms.date: 12/30/2016
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
ms.openlocfilehash: 5acf17b7c87a71259dba6579d8ee69e0eea86fa5
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738434"
---
# <a name="operator-windowsuixamlinteroptypename"></a>연산자 Windows::UI::Xaml::Interop::TypeName

`Platform::Type` 을 [Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename)으로 변환할 수 있습니다.

## <a name="syntax"></a>구문

```cpp
Operator TypeName(Platform::Type^ type);
```

### <a name="return-value"></a>반환 값

[이 제공되면](/uwp/api/windows.ui.xaml.interop.typename) Windows::UI::Xaml::Interop::TypeName `Platform::Type^`을 반환합니다.

### <a name="remarks"></a>설명

`TypeName` 은 형식 정보를 나타내기 위한 언어 중립 Windows 런타임 구조체입니다. [Platform::Type](../cppcx/platform-type-class.md) 은 C++에서만 사용되며 ABI(애플리케이션 이진 인터페이스) 전반에서 전달될 수 없습니다. 다음은 `TypeName`Navigate [함수에서](/uwp/api/windows.ui.xaml.controls.frame.navigate) 을 사용하는 한 가지 방법입니다.

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

### <a name="example"></a>예제

다음 예제에서는 `TypeName` 과 `Type`간을 변환하는 방법을 보여 줍니다.

```

// Convert from Type to TypeName
Windows::UI::Xaml::Interop::TypeName tn = TypeName(MainPage::typeid);

// Convert back from TypeName to Type
Type^ tx2 = (Type^)(tn);
```

## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값

.NET Framework는 `TypeName` 프로젝트를 [System.Type](assetId:///System.Type?qualifyHint=False&autoUpgrade=True)으로 변환할 수 있습니다.

### <a name="requirements"></a>요구 사항

## <a name="see-also"></a>참고자료

[연산자 Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Platform::Type 클래스](../cppcx/platform-type-class.md)
