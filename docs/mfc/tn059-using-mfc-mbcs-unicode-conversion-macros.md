---
title: 'TN059: MFC MBCS-유니코드 변환 매크로 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- MFCANS32.DLL
- Unicode [MFC], conversion macros
- Unicode [MFC], OLE interfaces
- conversion macros [MFC]
- converting Unicode
- MBCS [MFC], conversion macros
- macros [MFC], MBCS conversion macros
- TN059
ms.assetid: a2aab748-94d0-4e2f-8447-3bd07112a705
ms.openlocfilehash: 6c182ff584404fb91de8ff5e8020ec2e6ef9f950
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611864"
---
# <a name="tn059-using-mfc-mbcsunicode-conversion-macros"></a>TN059: MFC/유니코드 변환 매크로 사용

> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 참고 AFXPRIV에 정의 된/유니코드 변환 매크로 사용 하는 방법에 설명 합니다. 8. 이러한 매크로 해야 할 경우에 응용 프로그램 거래 직접 OLE API를 사용 하 여 또는 어떤 이유로 종종 유니코드 및 MBCS 변환에 가장 유용 합니다.

## <a name="overview"></a>개요

MFC의 3.x 특수 DLL 되었습니다 (MFCANS32를 사용 합니다. DLL) OLE 인터페이스 호출 된 경우 유니코드 및 MBCS 간에 자동으로 변환 합니다. 이 DLL가 쓸 처럼 OLE Api와 인터페이스 MBCS, 유니코드는 항상도 OLE 응용 프로그램을 허용 하는 거의 투명 한 계층 (macintosh 제외). 이 계층에서 편리 하 게 하는 동안으로 빠르게 이식할 수를 Win16에서 Win32로 응용 프로그램을 허용 하 고 (MFC, Microsoft Word, Microsoft Excel 및 VBA는이 기술을 사용 하는 Microsoft 응용 프로그램의 일부)에 현저한 성능 이었습니다 적중 합니다. 따라서 MFC 4.x이이 DLL을 사용 하지 않으며 대신 직접 유니코드 OLE 인터페이스에 설명 합니다. 이 위해 MFC OLE 인터페이스를 호출 하는 경우 유니코드에서 MBCS로 변환할 필요 하며 종종 OLE 인터페이스를 구현 하는 경우 유니코드에서 MBCS로 변환 합니다. 을 처리 하기 위해이 쉽고 효율적으로 다양 한 매크로이 변환을 쉽게 수행할 수 있도록 생성 되었습니다.

이러한 매크로 집합을 만드는 가장 큰 과제 중 하나에 메모리 할당입니다. 현재 위치에서 문자열을 변환할 수 없습니다, 때문에 변환된 결과를 저장할 새 메모리 할당 해야 합니다. 이 수행 하기 위해 다음과 유사한 코드를 사용 하 여:

```
// we want to convert an MBCS string in lpszA
int nLen = MultiByteToWideChar(CP_ACP,
    0,
    lpszA, -1,
    NULL,
    NULL);

LPWSTR lpszW = new WCHAR[nLen];
MultiByteToWideChar(CP_ACP,
    0,
    lpszA, -1,
    lpszW,
    nLen);

// use it to call OLE here
pI->SomeFunctionThatNeedsUnicode(lpszW);

// free the string
delete[] lpszW;
```

문제의 숫자로이 접근 방식입니다. 가장 큰 문제는 있다는 것을 많은 양의 코드를 작성, 테스트 및 디버그 합니다. 간단한 함수 호출이 있는 이제 훨씬 더 복잡 합니다. 또한이 과정에서 오버 헤드는 중요 한 런타임 있습니다. 메모리가 힙에 할당 되 고 변환 될 때마다 해제 해야 합니다. 마지막으로, 위 코드를 포함 해야 적절 한 `#ifdefs` (수행 되려면이 변환이 필요 하지 않습니다)는 유니코드 및 Macintosh 빌드에 대 한 추가 합니다.

우리가 솔루션 소스 코드는 1) 마스크 다양 한 플랫폼 및 2) 사용 하 여 효율적으로 메모리 할당 체계를 간의 차이점 및 3)은 기존에 삽입할 쉬운 몇 가지 매크로 만드는 것입니다. 정의의 한 예로 다음과 같습니다.

```
#define A2W(lpa) (\
((LPCSTR)lpa == NULL) NULL : (\
    _convert = (strnlen(lpa)+1),\
    AfxA2WHelper((LPWSTR) alloca(_convert*2),
    lpa,
    _convert)\)\)
```

이 위의 코드 대신 매크로 및 작업을 사용 하 여는 훨씬 간단 합니다.

```
// use it to call OLE here
USES_CONVERSION;
pI->SomeFunctionThatNeedsUnicode(T2OLE(lpszA));
```

여기서 변환이 필요한 이지만 매크로 사용 하 여 간단 하 고 효과적인 추가 호출이 있습니다.

힙 대신 스택에서 메모리를 할당할 인라이닝 _alloca () 함수를 사용 하는 각 매크로 구현 합니다. 스택에서 메모리를 할당 하는 것 보다 훨씬 힙에서 메모리를 할당 하 고 메모리는 함수가 종료 될 때 자동으로 해제 됩니다. 매크로 호출을 방지 하는 또한 `MultiByteToWideChar` (또는 `WideCharToMultiByte`) 두 번 이상. 필요한 것 보다 약간 더 많은 메모리를 할당 하면 됩니다. MBC를 하나의 변환 됩니다 알게 **WCHAR** 각 하 고 **WCHAR** 최대 두 MBC 바이트를 얻게 됩니다. 하지만 항상 충분히 약간 넘는 필요한 할당 하 여 변환을 처리 하기 위한 두 번째 호출은 두 번째 변환 함수 호출 수행 되지 않습니다. 도우미 함수에 대 한 호출 `AfxA2Whelper` 변환을 수행 하기 위해 수행 해야 하는 인수 푸시의 수를 줄입니다 (이 경우 더 작은 코드를 보다이 인해 `MultiByteToWideChar` 직접).

저장할 공간이 매크로 순서 대로 변환 매크로 사용 하는 작업을 위해 각 함수는 변환 (_c) 라는 지역 변수를 선언 하는 데 필요한 것, 임시 길이입니다. 이 예제에서 위와 같이 따라를 호출 하 여 이루어집니다.

일반 변환 매크로 OLE 특정 매크로가 있습니다. 이러한 두 가지 다른 매크로 집합 아래에 설명 되어 있습니다. 모든 매크로 AFXPRIV에 상주합니다. 8.

## <a name="generic-conversion-macros"></a>일반 변환 매크로

일반 변환 매크로 기본 메커니즘을 형성합니다. 매크로 예제 및 A2W, 이전 섹션에 나온 이러한 단일 "일반" 매크로 합니다. 관련 되지 않은 OLE를 구체적으로 합니다. 제네릭 매크로 집합은 다음과 같습니다.

```
A2CW      (LPCSTR) -> (LPCWSTR)
A2W      (LPCSTR) -> (LPWSTR)
W2CA      (LPCWSTR) -> (LPCSTR)
W2A      (LPCWSTR) -> (LPSTR)
```

텍스트 변환 작업을 수행 하는 것 외에도 밖에도 매크로 및 변환 하기 위한 도우미 함수 `TEXTMETRIC`, `DEVMODE`, `BSTR`, 및 OLE 문자열을 할당 합니다. 이러한 매크로이 기사의 범위를 벗어나는-AFXPRIV를 가리킵니다. 이러한 매크로 대 한 자세한 내용은 H입니다.

## <a name="ole-conversion-macros"></a>OLE 변환 매크로

OLE 변환 매크로 처리 하는 함수에 맞게 설계 되었습니다 **OLESTR** 문자입니다. 많은 참조를 볼는 OLE 머리글을 살펴보면 **LPCOLESTR** 하 고 **OLECHAR**합니다. 이러한 형식은 플랫폼에 특정 하지 않은 방식으로 OLE 인터페이스에 사용 된 문자의 형식을 참조 하도록 사용 됩니다. **OLECHAR** 매핑됩니다 **char** Win16 및 Macintosh 플랫폼에서와 **WCHAR** Win32에서.

횟수를 유지 하기 위해 **#ifdef** MFC의 지시문 코드를 최소한으로 각 변환에 대 한 유사한 매크로 있다고 하는 OLE 문자열이 포함 되어 있는 합니다. 다음 매크로 가장 일반적으로 사용 됩니다.

```
T2COLE   (LPCTSTR) -> (LPCOLESTR)
T2OLE   (LPCTSTR) -> (LPOLESTR)
OLE2CT   (LPCOLESTR) -> (LPCTSTR)
OLE2T   (LPCOLESTR) -> (LPCSTR)
```

마찬가지로 TEXTMETRIC, DEVMODE, BSTR, 및 문자열을 할당 하는 OLE를 수행 하기 위한 비슷한 매크로 있습니다. AFXPRIV를 참조 하십시오. 자세한 H입니다.

## <a name="other-considerations"></a>기타 고려 사항

빽빽한 루프에서 매크로 사용 하지 마세요. 예를 들어, 다음 종류의 코드를 작성 하지 않을 수 있습니다.

```
void BadIterateCode(LPCTSTR lpsz)
{
    USES_CONVERSION;
    for (int ii = 0; ii <10000; ii++)
    pI->SomeMethod(ii, T2COLE(lpsz));

}
```

위의 코드에서 문자열의 내용에 따라 스택에 메모리의 메가바이트 할당 될 수 있습니다 `lpsz` 됩니다! 루프의 각 반복에 대 한 문자열을 변환 하는 데 시간이 걸립니다. 대신 이러한 상수 변환이 루프 밖으로 이동 합니다.

```
void MuchBetterIterateCode(LPCTSTR lpsz)
{
    USES_CONVERSION;
    LPCOLESTR lpszT = T2COLE(lpsz);

    for (int ii = 0; ii <10000; ii++)
    pI->SomeMethod(ii, lpszT);

}
```

문자열 상수 없는 경우 다음 함수에는 메서드를 캡슐화 합니다. 이렇게 하면 변환 버퍼 때마다를 해제할 수 있습니다. 예를 들어:

```
void CallSomeMethod(int ii, LPCTSTR lpsz)
{
    USES_CONVERSION;
    pI->SomeMethod(ii, T2COLE(lpsz));

}

void MuchBetterIterateCode2(LPCTSTR* lpszArray)
{
    for (int ii = 0; ii <10000; ii++)
    CallSomeMethod(ii, lpszArray[ii]);

}
```

반환 값을 반환 하기 전에 데이터의 복사본을 의미 하지 않는 한, 매크로 중 하나의 결과 반환 하지 않습니다. 예를 들어, 다음이 코드는 잘못 되었습니다.

```
LPTSTR BadConvert(ISomeInterface* pI)
{
    USES_CONVERSION;
    LPOLESTR lpsz = NULL;
    pI->GetFileName(&lpsz);

LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

return lpszT; // bad! returning alloca memory
}
```

위의 코드 값을 복사 하는 반환 값을 변경 하 여 해결할 수 없습니다.

```
CString BetterConvert(ISomeInterface* pI)
{
    USES_CONVERSION;
    LPOLESTR lpsz = NULL;
    pI->GetFileName(&lpsz);

LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

return lpszT; // CString makes copy
}
```

매크로 쉽고 사용 하기 쉬운 코드를 삽입 하는 위의 주의에서 알 수 있듯이, 사용 하는 경우 주의 해야 합니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
