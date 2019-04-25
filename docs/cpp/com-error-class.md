---
title: _com_error 클래스
ms.date: 11/04/2016
f1_keywords:
- _com_error
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
ms.openlocfilehash: 8ed1521cbf768e5b473281e5f9b7c6597cdc4692
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155204"
---
# <a name="comerror-class"></a>_com_error 클래스

**Microsoft 전용**

A **_com_error** 개체 형식 라이브러리에서 생성 된 헤더 파일의 오류 처리 래퍼 함수를 통해 또는 COM 지원 클래스 중 하나를 검색 하는 예외 상태를 나타냅니다. 합니다 **_com_error** HRESULT 오류 코드 및 연결 된 클래스에서 캡슐화 `IErrorInfo Interface` 개체입니다.

### <a name="construction"></a>생성

|||
|-|-|
|[_com_error](../cpp/com-error-com-error.md)|생성 된 **_com_error** 개체입니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[operator =](../cpp/com-error-operator-equal.md)|기존 할당 **_com_error** 다른 개체입니다.|

### <a name="extractor-functions"></a>Extractor 함수

|||
|-|-|
|[오류](../cpp/com-error-error.md)|생성자에 전달 된 HRESULT를 검색 합니다.|
|[ErrorInfo](../cpp/com-error-errorinfo.md)|검색 된 `IErrorInfo` 개체 생성자에 전달 합니다.|
|[WCode](../cpp/com-error-wcode.md)|캡슐화 된 HRESULT에 매핑된 16 비트 오류 코드를 검색 합니다.|

### <a name="ierrorinfo-functions"></a>IErrorInfo 함수

|||
|-|-|
|[설명](../cpp/com-error-description.md)|호출 `IErrorInfo::GetDescription` 함수입니다.|
|[HelpContext](../cpp/com-error-helpcontext.md)|호출 `IErrorInfo::GetHelpContext` 함수입니다.|
|[HelpFile](../cpp/com-error-helpfile.md)|호출 `IErrorInfo::GetHelpFile` 함수|
|[소스](../cpp/com-error-source.md)|호출 `IErrorInfo::GetSource` 함수입니다.|
|[GUID](../cpp/com-error-guid.md)|호출 `IErrorInfo::GetGUID` 함수입니다.|

### <a name="format-message-extractor"></a>형식 메시지 추출기

|||
|-|-|
|[ErrorMessage](../cpp/com-error-errormessage.md)|에 저장 된 HRESULT에 대 한 문자열 메시지를 검색 합니다 **_com_error** 개체입니다.|

### <a name="exepinfowcode-to-hresult-mappers"></a>HRESULT 매퍼를 ExepInfo.wCode

|||
|-|-|
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|16 비트에서 32 비트 HRESULT 매핑됩니다 `wCode`합니다.|
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|16 비트 매핑합니다 `wCode` 32 비트 hresult입니다.|

**Microsoft 전용 종료**

## <a name="requirements"></a>요구 사항

**헤더:** \<comdef.h >

`Lib:` 에서는 comsuppw.lib 또는 comsuppwd.lib (참조 [/zc: wchar_t (wchar_t는 네이티브 형식임)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 자세한)

## <a name="see-also"></a>참고자료

[컴파일러 COM 지원 클래스](../cpp/compiler-com-support-classes.md)<br/>
[IErrorInfo 인터페이스](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)