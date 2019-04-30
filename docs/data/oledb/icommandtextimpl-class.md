---
title: ICommandTextImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- ICommandText
- GetCommandText
- ICommandTextImpl.GetCommandText
- ICommandTextImpl::GetCommandText
- ATL::ICommandTextImpl::m_strCommandText
- ICommandTextImpl<T>::m_strCommandText
- m_strCommandText
- ICommandTextImpl.m_strCommandText
- ICommandTextImpl::m_strCommandText
- ATL::ICommandTextImpl<T>::m_strCommandText
- ATL.ICommandTextImpl.m_strCommandText
- ICommandTextImpl.SetCommandText
- ICommandTextImpl::SetCommandText
- SetCommandText
helpviewer_keywords:
- ICommandText class
- GetCommandText method
- m_strCommandText
- SetCommandText method
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
ms.openlocfilehash: de9e930056db7b91968ca1ce471a87809693376a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408981"
---
# <a name="icommandtextimpl-class"></a>ICommandTextImpl 클래스

에 대 한 구현을 제공 합니다 [ICommandText](/previous-versions/windows/desktop/ms714914(v=vs.85)) 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
template <class T >
class ATL_NO_VTABLE ICommandTextImpl
   : public ICommandImpl<T, ICommandText>
```

### <a name="parameters"></a>매개 변수

*T*<br/>
명령 클래스에서 파생 된 `ICommandTextImpl`합니다.

## <a name="requirements"></a>요구 사항

**헤더:** altdb.h

## <a name="members"></a>멤버

### <a name="interface-methods"></a>인터페이스 메서드

|||
|-|-|
|[GetCommandText](#getcommandtext)|마지막 호출에 의해 설정 텍스트 명령을 반환 [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)합니다.|
|[SetCommandText](#setcommandtext)|기존 명령 텍스트를 대체 하는 명령 텍스트에 설정 합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[m_strCommandText](#strcommandtext)|명령 텍스트를 저장합니다.|

## <a name="remarks"></a>설명

명령에는 필수 인터페이스입니다.

## <a name="getcommandtext"></a> ICommandTextImpl::GetCommandText

마지막 호출에 의해 설정 텍스트 명령을 반환 [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(GetCommandText)(GUID * pguidDialect,
   LPOLESTR * ppwszCommand);
```

#### <a name="parameters"></a>매개 변수

참조 [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다. 합니다 *pguidDialect* 기본적으로 매개 변수가 무시 됩니다.

## <a name="setcommandtext"></a> ICommandTextImpl::SetCommandText

기존 명령 텍스트를 대체 하는 명령 텍스트에 설정 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(SetCommandText)(REFGUID rguidDialect,
   LPCOLESTR pwszCommand);
```

#### <a name="parameters"></a>매개 변수

참조 [icommandtext:: Setcommandtext](/previous-versions/windows/desktop/ms709757(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="strcommandtext"></a> ICommandTextImpl::m_strCommandText

명령 텍스트 문자열을 저장합니다.

### <a name="syntax"></a>구문

```cpp
CComBSTR m_strCommandText;
```

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)