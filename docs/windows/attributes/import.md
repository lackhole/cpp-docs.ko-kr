---
title: 가져오기 (C++ COM 특성)
ms.date: 10/03/2018
f1_keywords:
- vc-attr.import
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
ms.openlocfilehash: d458ce9d938da5f3650eb2478385165de6a140ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409383"
---
# <a name="import"></a>import

주 프로그램 IDL에서 참조 하려는 정의 포함 하는 다른.idl,.odl, 또는 헤더 파일을 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ import(
   idl_file
) ];
```

### <a name="parameters"></a>매개 변수

*idl_file*<br/>
현재 프로젝트의 형식 라이브러리에 가져와서 원하는.idl 파일의 이름입니다.

## <a name="remarks"></a>설명

**가져오기** C++ 원인 특성는 `#import` 문 아래에 배치 하는 `import "docobj.idl"` 생성 된.idl 파일의 문. **가져오기** 특성에 동일한 기능을 합니다 [가져오기](/windows/desktop/Midl/import) MIDL 특성입니다.

**가져올** 만 특성; 프로젝트에서 생성 되는.idl 파일에 지정된 된 파일을 배치 합니다 **가져오기** 특성 수 없다는 소스 코드에서 지정된 된 파일의 생성 호출 프로젝트입니다.  프로젝트의 소스 코드에서 지정된 된 파일의 구문을 호출을 사용 하거나 [#import](../../preprocessor/hash-import-directive-cpp.md) 및 `embedded_idl` 특성 이거나.h 파일을 포함할 수 있습니다 합니다 *idl_file*.h 파일이 있는 경우, 합니다.

## <a name="example"></a>예제

다음 예를 참조하십시오.

```cpp
// cpp_attr_ref_import.cpp
// compile with: /LD
[module(name="MyLib")];
[import(import.idl)];
```

생성된 된.idl 파일에 다음 코드를 생성합니다.

```
import "docobj.idl";
import "import.idl";

[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]
library MyLib {
   importlib("stdole2.tlb");
   importlib("olepro32.dll");
...
```

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|원하는 위치|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)<br/>
[독립 실행형 특성](stand-alone-attributes.md)<br/>
[importidl](importidl.md)<br/>
[importlib](importlib.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)