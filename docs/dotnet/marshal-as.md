---
title: marshal_as
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- marshal_as
- msclr.interop.marshal_as
- msclr::interop::marshal_as
helpviewer_keywords:
- marshal_as template [C++]
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
ms.openlocfilehash: 2294d8fe94a32f281332c963b21a542366ae3207
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751508"
---
# <a name="marshalas"></a>marshal_as

이 메서드는 네이티브 및 관리 되는 환경 간에 데이터를 변환합니다.

## <a name="syntax"></a>구문

```
To_Type marshal_as<To_Type>(
   From_Type input
);
```

#### <a name="parameters"></a>매개 변수

*input*<br/>
[in] 에 마샬링하 려는 값을 `To_Type` 변수입니다.

## <a name="return-value"></a>반환 값

형식 변수의 `To_Type` 으로 변환된 된 값 즉 `input`합니다.

## <a name="remarks"></a>설명

이 방법은 네이티브 및 관리 되는 형식 간에 데이터를 변환 하는 간단한 방법을 설명 합니다. 확인 하려면 지 원하는 데이터 형식을 참조 하십시오 [Overview of Marshaling c + +에서](../dotnet/overview-of-marshaling-in-cpp.md)합니다. 일부 데이터 변환을 컨텍스트가 필요 합니다. 사용 하 여 해당 데이터 형식을 변환할 수는 [marshal_context 클래스](../dotnet/marshal-context-class.md)합니다.

지원 되지 않는 데이터 형식의 쌍 마샬링할 하려고 하면 `marshal_as` 오류가 생성 됩니다 [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) 컴파일 타임에 있습니다. 자세한 내용은이 오류와 함께 제공 되는 메시지를 읽습니다. `C4996` 이상만 사용 되지 않는 함수에 대 한 오류를 생성할 수 있습니다. 이러한 예로 한 쌍의 지원 되지 않는 데이터 형식 마샬링하 하려고 합니다.

마샬링 라이브러리는 몇 가지 헤더 파일의 구성 됩니다. 변환 파일을 하나만 이어야 하는데 다른 변환 해야 할 경우 추가 파일을 포함할 수 있습니다. 변환은 파일을 사용 하 여 연결을 보려면 테이블에서 확인 `Marshaling Overview`합니다. 와 상관 없이 어떤 변환 수행 하려는, 네임 스페이스는 항상 적용에서 합니다.

## <a name="example"></a>예제

이 예제에서 마샬링합니다를 `const char*` 에 `System::String` 변수 형식입니다.

```
// marshal_as_test.cpp
// compile with: /clr
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   const char* message = "Test String to Marshal";
   String^ result;
   result = marshal_as<String^>( message );
   return 0;
}
```

## <a name="requirements"></a>요구 사항

**헤더 파일:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, 또는 \<msclr\marshal_atl.h >

**Namespace:** msclr::interop

## <a name="see-also"></a>참고자료

[C++ 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_context 클래스](../dotnet/marshal-context-class.md)
