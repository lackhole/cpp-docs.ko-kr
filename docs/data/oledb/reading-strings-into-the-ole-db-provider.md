---
title: OLE DB 공급자로 문자열 읽어들이기
ms.date: 10/13/2018
helpviewer_keywords:
- OLE DB providers, reading strings into
ms.assetid: 517f322c-f37e-4eed-bf5e-dd9a412c2f98
ms.openlocfilehash: d46b4e1a53e7e489763f40e7a5238e65b493f7c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62283847"
---
# <a name="reading-strings-into-the-ole-db-provider"></a>OLE DB 공급자로 문자열 읽어들이기

`CCustomRowset::Execute` 함수 파일을 열고 문자열을 읽습니다. 소비자를 호출 하 여 공급자에 게 파일 이름을 전달 [icommandtext:: Setcommandtext](/previous-versions/windows/desktop/ms709757(v=vs.85))합니다. 공급자 파일 이름을 받고 멤버 변수에 저장 `m_strCommandText`합니다. `Execute` 파일 이름을 읽고 `m_strCommandText`합니다. 파일 이름이 잘못 되었거나 파일을 사용할 수 없는 경우 `Execute` 오류를 반환 합니다. 을 열고 파일 및 호출 `fgets` 문자열을 검색 합니다. 각 설정 문자열의 읽기에 대 한 `Execute` 사용자 레코드의 인스턴스를 만듭니다 (수정 `CCustomWindowsFile` 에서 [OLE DB 공급자에 문자열 저장](../../data/oledb/storing-strings-in-the-ole-db-provider.md)) 배열에 넣습니다.

파일을 열 수 없는 경우 `Execute` DB_E_NOTABLE 반환 해야 합니다. E_FAIL을 대신 반환 하는 경우 공급자를 많은 소비자와 함께 작동 하지 않습니다 하 고 OLE DB를 전달 하지 않습니다 [적합성 테스트](../../data/oledb/testing-your-provider.md)합니다.

## <a name="example"></a>예제

```cpp
/////////////////////////////////////////////////////////////////////////
// CustomRS.h
class CCustomRowset : public CRowsetImpl< CCustomRowset, CCustomWindowsFile, CCustomCommand>
{
public:
    HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)
    {
        enum {
            sizeOfBuffer = 256,
            sizeOfFile = MAX_PATH
        };
        USES_CONVERSION;
        FILE* pFile = NULL;
        TCHAR szString[sizeOfBuffer];
        TCHAR szFile[sizeOfFile];
        size_t nLength;

        ObjectLock lock(this);

        // From a filename, passed in as a command text, scan the file
        // placing data in the data array.
        if (!m_strCommandText)
        {
            ATLTRACE("No filename specified");
            return E_FAIL;
        }

        // Open the file
        _tcscpy_s(szFile, sizeOfFile, m_strCommandText);
        if (szFile[0] == _T('\0') ||
            (fopen_s(&pFile, (char*)&szFile[0], "r") == 0))
        {
            ATLTRACE("Could not open file");
            return DB_E_NOTABLE;
        }

        // Scan and parse the file.
        // The file should contain two strings per record
        LONG cFiles = 0;
        while (fgets((char*)szString, sizeOfBuffer, pFile) != NULL)
        {
            nLength = strnlen((char*)szString, sizeOfBuffer);
            szString[nLength-1] = '\0';   // Strip off trailing CR/LF
            CCustomWindowsFile am;
            _tcscpy_s(am.szCommand, am.iSize, szString);
            _tcscpy_s(am.szCommand2, am.iSize, szString);

            if (fgets((char*)szString, sizeOfBuffer, pFile) != NULL)
            {
                nLength = strnlen((char*)szString, sizeOfBuffer);
                szString[nLength-1] = '\0'; // Strip off trailing CR/LF
                _tcscpy_s(am.szText, am.iSize, szString);
                _tcscpy_s(am.szText2, am.iSize, szString);
            }

            am.dwBookmark = ++cFiles;
            if (!m_rgRowData.Add(am))
            {
                ATLTRACE("Couldn't add data to array");
                fclose(pFile);
                return E_FAIL;
            }
        }

        if (pcRowsAffected != NULL)
            *pcRowsAffected = cFiles;
        return S_OK;
    }
};
```

이 완료 되 면 공급자 컴파일 및 실행을 준비 해야 합니다. 공급자를 테스트 하려면이 기능을 일치 하는 소비자가 있어야 합니다. [단순 소비자 구현](../../data/oledb/implementing-a-simple-consumer.md) 에서 테스트 소비자를 만드는 방법을 보여 줍니다. 공급자를 사용 하 여 테스트 소비자를 실행 하 고 테스트 소비자 공급자에서 적절 한 문자열을 검색 하는 확인 합니다.

공급자를 성공적으로 테스트 하는 경우에 추가 인터페이스를 구현 하 여 해당 기능을 개선 하는 것이 좋습니다. 예제에 표시 됩니다 [간단한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)합니다.

## <a name="see-also"></a>참고자료

[단순한 읽기 전용 공급자 구현](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>
