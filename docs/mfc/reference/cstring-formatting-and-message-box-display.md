---
title: CString 서식 지정 및 메시지 상자 표시
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects [MFC], formatting and message boxes
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
ms.openlocfilehash: ad880c5302fd2274c5d46719e912461fd7497f10
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611018"
---
# <a name="cstring-formatting-and-message-box-display"></a>CString 서식 지정 및 메시지 상자 표시

서식을 지정 하 고 구문 분석 다양 한 함수가 제공 됩니다 `CString` 개체입니다. 조작 해야 때마다 이러한 함수를 사용할 수 있습니다 `CString` 하지만 개체는 메시지 상자 텍스트에 표시 되는 문자열 형식 지정 하는 데 특히 유용 합니다.

이 그룹의 함수에는 메시지 상자를 표시 하는 것에 대 한 전역 루틴이 포함 되어 있습니다.

### <a name="cstring-functions"></a>CString 함수

|||
|-|-|
|[AfxExtractSubString](#afxextractsubstring)|지정 된 소스 문자열에서 단일 문자를 구분 하는 부분 문자열을 추출 합니다.|
|[AfxFormatString1](#afxformatstring1)|대체 문자열 테이블에 포함 된 문자열의 서식 문자 "%1"에 지정된 된 문자열입니다.|
|[AfxFormatString2](#afxformatstring2)|형식에 대 한 대체 두 문자열 "%1" 및 "%2" 문자열에서 문자열 테이블에 포함 된 문자입니다.|
|[AfxMessageBox](#afxmessagebox)|메시지 상자를 표시합니다.|

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

##  <a name="afxextractsubstring"></a>  AfxExtractSubString

지정 된 소스 문자열에서 부분 문자열을 추출 하려면이 전역 함수를 사용할 수 있습니다.

```
BOOL AFXAPI AfxExtractSubString (
    CString& rString,
    LPCTSTR lpszFullString,
    int iSubString,
    TCHAR chSep  = '\n');
```

### <a name="parameters"></a>매개 변수

*rString*<br/>
에 대 한 참조를 [CString](../../atl-mfc-shared/using-cstring.md) 는 개별 부분 문자열을 받게 될 개체입니다.

*lpszFullString*<br/>
추출 하는 문자열의 전체 텍스트를 포함 하는 문자열입니다.

*iSubString*<br/>
추출할 부분 문자열의 0 기반 인덱스 *lpszFullString*합니다.

*chSep*<br/>
부분 문자열을 구분 하는 데 사용 되는 구분 기호 문자입니다.

### <a name="return-value"></a>반환 값

함수는 제공 된 인덱스에 있는 부분 문자열을 성공적으로 추출 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 함수는 각 부분 문자열을 구분 하는 알려진된 단일 문자 소스 문자열에서 여러 부분 문자열을 추출 하는 데 유용 합니다. 이 함수 시작 부분에서 검색 된 *lpszFullString* 매개 변수를 호출할 때마다 합니다.

경우이 함수는 FALSE를 반환 *lpszFullString* 가 NULL로 설정 하거나 함수 끝에 도달할 *lpszFullString* 찾기 없이 *iSubString*+ 1 지정 된 구분 기호 문자를 발견 합니다. 합니다 *rString* 매개 변수는 경우 원래 값에서 수정 되지 것입니다 *lpszFullString* 하 고, 그렇지 않으면 NULL 설정한 합니다 *rString* 매개 변수는 빈 문자열로 설정 하는 경우 지정된 된 인덱스에 대 한 부분 문자열을 추출할 수 없습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#48](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_1.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

##  <a name="afxformatstring1"></a>  AfxFormatString1

가리키는 문자열 대체 *lpsz1* 식별 되는 템플릿 문자열 리소스에서 문자 "%1"의 모든 인스턴스에 대 한 *nIDS*합니다.

```
void  AfxFormatString1(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1);
```

### <a name="parameters"></a>매개 변수

*rString*<br/>
대체가 수행된 후 결과 문자열을 포함하는 `CString` 개체에 대한 참조입니다.

*nIDS*<br/>
대체가 수행될 템플릿 문자열의 리소스 ID입니다.

*lpsz1*<br/>
템플릿 문자열에서 서식 문자 "%1"을(를) 대체하는 문자열입니다.

### <a name="remarks"></a>설명

새로 구성 된 문자열에 저장 됩니다 *rString*합니다. 예를 들어 문자열 테이블에 있는 문자열은 "File %1 찾을 수 없습니다"와 *lpsz1* 과 "C:\MYFILE 같음. TXT", 한 다음 *rString* "C:\MYFILE 파일 문자열이 포함 됩니다.입니다. TXT 찾을 수 없습니다 ". 이 함수는 메시지 상자와 다른 창에 서식 지정 문자열을 전송하는 데 유용합니다.

서식 문자 "%1"이(가) 두 번 이상 문자열에 나타나는 경우 대체가 여러 번 수행됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#25](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_2.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

##  <a name="afxformatstring2"></a>  AfxFormatString2

가리키는 문자열 대체 *lpsz1* 문자 "%1"의 모든 인스턴스를 가리키는 문자열 *lpsz2* 템플릿 문자열 리소스에서 문자 "%2"의 모든 인스턴스에 대 한 로 식별 *nIDS*합니다.

```
void AfxFormatString2(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1,
    LPCTSTR lpsz2);
```

### <a name="parameters"></a>매개 변수

*rString*<br/>
에 대 한 참조를 `CString` 대체가 수행 된 후 결과 문자열을 포함 하는 합니다.

*nIDS*<br/>
대체를 수행 합니다 하는 템플릿 문자열의 문자열 테이블 ID입니다.

*lpsz1*<br/>
템플릿 문자열에서 서식 문자 "%1"을(를) 대체하는 문자열입니다.

*lpsz2*<br/>
템플릿 문자열에서 문자 "%2"를 형식으로 대체할 문자열입니다.

### <a name="remarks"></a>설명

새로 구성 된 문자열에 저장 됩니다 *rString*합니다. 예를 들어 문자열 테이블의 문자열은 "%2 디렉터리에서 찾을 수 없습니다 %1 파일" *lpsz1* "MYFILE 가리키는. TXT", 및 *lpsz2* 한 다음"C:\MYDIR "를 가리키는 *rString* "File MYFILE 문자열이 포함 됩니다. TXT C:\MYDIR 디렉터리에서 찾을 수 없습니다 "

형식 문자 "%1" 또는 "%2" 문자열에 두 번 이상 나타나는 경우 대체가 여러 수행 됩니다. 숫자 순서로 필요가 없습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#26](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_3.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

##  <a name="afxmessagebox"></a>  AfxMessageBox

화면에 메시지 상자를 표시 합니다.

```
int AfxMessageBox(
    LPCTSTR lpszText,
    UINT nType = MB_OK,
    UINT nIDHelp = 0);

int AFXAPI AfxMessageBox(
    UINT nIDPrompt,
    UINT nType = MB_OK,
    UINT nIDHelp = (UINT) -1);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
가리키는 `CString` 개체나 메시지 상자에 표시할 메시지가 포함 된 null로 끝나는 문자열입니다.

*nType*<br/>
메시지 상자의 스타일입니다. 적용 된 [메시지 상자 스타일](../../mfc/reference/styles-used-by-mfc.md#message-box-styles) 상자로 합니다.

*nIDHelp*<br/>
메시지에 대 한 도움말 컨텍스트 ID 0 응용 프로그램의 기본 도움말 컨텍스트가 사용 됨을 나타냅니다.

*nIDPrompt*<br/>
문자열 테이블의 문자열을 참조 하는 데 사용 하는 고유 ID입니다.

### <a name="return-value"></a>반환 값

메시지 상자를 표시할 충분 한 메모리가 없을 경우 0 그렇지 않으면 다음 값 중 하나가 반환 됩니다.

- IDABORT 중단 단추를 선택 했습니다.

- IDCANCEL 취소 단추를 선택 했습니다.

- IDIGNORE 무시 단추를 선택 했습니다.

- IDNO 없습니다 단추를 선택 했습니다.

- IDOK 확인 단추를 선택 했습니다.

- IDRETRY 다시 시도 단추를 선택 했습니다.

- IDYES 예 단추를 선택 했습니다.

메시지 상자에 취소 단추, ESC 키를 누르면 또는 취소 단추를 선택한 경우 IDCANCEL 값 반환 됩니다. 메시지 상자에 취소 단추가 있는 경우 ESC 키를 눌러 효과가 없습니다.

함수 [AfxFormatString1](#afxformatstring1) 하 고 [AfxFormatString2](#afxformatstring2) 메시지 상자에 표시 되는 텍스트 서식 지정 하는 데 유용할 수 있습니다.

### <a name="remarks"></a>설명

이 첫 번째 폼은 가리키는 텍스트 문자열을 표시 합니다. 함수 오버 로드 *lpszText* 메시지 상자를 사용 하 여 *nIDHelp* 도움말 컨텍스트를 설명 합니다. 도움말 컨텍스트 (일반적으로 F1)의 도움말 키를 누를 때 관련된 된 도움말 항목으로 이동 됩니다.

ID를 사용 하 여 문자열 리소스를 사용 하는 함수의 두 번째 형태 *nIDPrompt* 메시지 상자에는 메시지를 표시 합니다. 값을 통해 관련된 도움말 페이지는 찾을 *nIDHelp*합니다. 경우 기본값인 *nIDHelp* 은 사용 되는 (-1), 문자열 리소스 ID *nIDPrompt*, 도움말 컨텍스트에 사용 됩니다. 도움말 컨텍스트를 정의 하는 방법에 대 한 자세한 내용은 참조 하십시오 [Technical Note 28](../../mfc/tn028-context-sensitive-help-support.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#133](../../mfc/reference/codesnippet/cpp/cstring-formatting-and-message-box-display_4.cpp)]

## <a name="see-also"></a>참고자료

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CStringT 클래스](../../atl-mfc-shared/reference/cstringt-class.md)
