---
title: marshal_context 클래스
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::interop::marshal_context::marshal_context
- msclr::interop::marshal_context::marshal_as
helpviewer_keywords:
- msclr::marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
ms.openlocfilehash: 25fc2be80ba0e5d8c7f76cee1f22eed4d1bb4fc7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384870"
---
# <a name="marshalcontext-class"></a>marshal_context 클래스

이 클래스는 네이티브 및 관리 되는 환경 간에 데이터를 변환합니다.

## <a name="syntax"></a>구문

```cpp
class marshal_context
```

## <a name="remarks"></a>설명

사용 된 `marshal_context` 컨텍스트를 필요로 하는 데이터 변환에 대 한 클래스입니다. 변환이 필요한 컨텍스트 및 마샬링 파일에 포함 되도록 하는 방법에 대 한 자세한 내용은 참조 하세요. [마샬링 개요 C++ ](../dotnet/overview-of-marshaling-in-cpp.md)합니다. 마샬링 컨텍스트를 사용 하는 경우의 결과 까지만 유효 합니다 `marshal_context` 개체는 소멸 됩니다. 결과 유지 하려면 데이터를 복사 해야 합니다.

동일한 `marshal_context` 다양 한 데이터 변환에 사용할 수 있습니다. 이 방식으로 컨텍스트를 다시 사용 마샬링 이전 호출의 결과 영향을 주지 않습니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명| 
|---------|-----------| 
|[marshal_context::marshal_context](#marshal-context)|생성 된 `marshal_context` 관리 및 네이티브 데이터 형식 간의 데이터 변환에 사용할 개체입니다.| 
|[marshal_context::~marshal_context](#tilde-marshal-context)|`marshal_context` 개체를 제거합니다.| 

### <a name="public-methods"></a>public 메서드

|이름|설명| 
|---------|-----------| 
|[marshal_context::marshal_as](#marshal-as)|특정 데이터 개체를 관리 및 네이티브 데이터 형식 간에 변환할 마샬링을 수행 합니다.| 


## <a name="requirements"></a>요구 사항

**헤더 파일:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, 또는 \<msclr\marshal_atl.h >

**Namespace:** msclr::interop

## <a name="marshal-context"></a>marshal_context::marshal_context

생성 된 `marshal_context` 관리 및 네이티브 데이터 형식 간의 데이터 변환에 사용할 개체입니다.

```cpp
marshal_context();
```

### <a name="remarks"></a>설명

일부 데이터 변환을 마샬링 컨텍스트가 필요 합니다. 번역에 대 한 자세한 컨텍스트를 필요를 응용 프로그램에 포함 해야 합니다는 마샬링 파일을 참조 하세요 [마샬링 개요 C++ ](../dotnet/overview-of-marshaling-in-cpp.md)합니다.

### <a name="example"></a>예제

예를 참조 하세요 [marshal_context:: marshal_as](../dotnet/marshal-context-marshal-as.md)합니다.


## <a name="tilde-marshal-context"></a>marshal_context::~marshal_context

`marshal_context` 개체를 제거합니다.

```cpp
~marshal_context();
```

### <a name="remarks"></a>설명

일부 데이터 변환을 마샬링 컨텍스트가 필요 합니다. 참조 [마샬링 개요 C++ ](../dotnet/overview-of-marshaling-in-cpp.md) 는 번역 컨텍스트 하며 응용 프로그램에 포함할 마샬링 파일에 대 한 자세한 내용은 합니다.

삭제를 `marshal_context` 개체 컨텍스트에서 변환 데이터를 무효화 됩니다. 이후에 데이터를 보존 하려는 경우를 `marshal_context` 개체 삭제 되 면 유지 되는 변수에 데이터를 수동으로 복사 해야 합니다.

## <a name="marshal-as"></a>marshal_context::marshal_as

특정 데이터 개체를 관리 및 네이티브 데이터 형식 간에 변환할 마샬링을 수행 합니다.

```cpp
To_Type marshal_as<To_Type>(
   From_Type input
);
```

### <a name="parameters"></a>매개 변수

*input*<br/>
[in] 에 마샬링하 려는 값을 `To_Type` 변수입니다.

### <a name="return-value"></a>반환 값

형식 변수의 `To_Type` 의 변환 된 값인는 `input`합니다.

### <a name="remarks"></a>설명

이 함수는 특정 데이터 개체의 마샬링을 수행 합니다. 이 함수를 사용 하 여 테이블에서 지정 된 변환 만으로 [마샬링 개요 C++ ](../dotnet/overview-of-marshaling-in-cpp.md)합니다.

지원 되지 않는 데이터 형식의 쌍 마샬링할 하려고 하면 `marshal_as` 오류가 생성 됩니다 [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) 컴파일 타임에 있습니다. 자세한 내용은이 오류와 함께 제공 되는 메시지를 읽습니다. `C4996` 이상만 사용 되지 않는 함수에 대 한 오류를 생성할 수 있습니다. 이 오류를 생성 하는 두 가지 조건은를 지원 하지 않는 데이터 형식의 한 쌍을 마샬링하는 동안 하며 사용 하는 동안 `marshal_as` 필요한 컨텍스트를 변환 합니다.

마샬링 라이브러리는 몇 가지 헤더 파일의 구성 됩니다. 변환 파일을 하나만 이어야 하는데 다른 변환 해야 할 경우 추가 파일을 포함할 수 있습니다. 표의 `Marshaling Overview in C++` 나타냅니다 마샬링 파일 각 변환에 포함 해야 합니다.

### <a name="example"></a>예제

마샬링에 대 한 컨텍스트를 만드는이 예제는 `System::String` 에 `const char *` 변수 형식입니다. 변환된 된 데이터 컨텍스트를 삭제 하는 줄 뒤에 유효 하지 않습니다.

```cpp
// marshal_context_test.cpp
// compile with: /clr
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   marshal_context^ context = gcnew marshal_context();
   String^ message = gcnew String("Test String to Marshal");
   const char* result;
   result = context->marshal_as<const char*>( message );
   delete context;
   return 0;
}
```