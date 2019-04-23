---
title: CCustomWindowsFile
ms.date: 10/22/2018
f1_keywords:
- cmyproviderwindowsfile
- ccustomwindowsfile
helpviewer_keywords:
- CMyProviderWindowsFile class
- OLE DB providers, wizard-generated files
- CCustomWindowsFile class
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
ms.openlocfilehash: 4af302d8a391de359f3b8ac66d41b5d7198fd8f6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033126"
---
# <a name="ccustomwindowsfile"></a>CCustomWindowsFile

마법사의 데이터 행이 있는 클래스를 만듭니다. 이 경우에 호출 됩니다 `CCustomWindowsFile`합니다. 다음 코드에 대 한 `CCustomWindowsFile` 마법사에서 생성 되 고 사용 하 여 디렉터리의 모든 파일을 나열 합니다 `WIN32_FIND_DATA` 구조입니다. `CCustomWindowsFile` 상속 되는 `WIN32_FIND_DATA` 구조:

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H

class CCustomWindowsFile: 
   public WIN32_FIND_DATA
{
public:
BEGIN_PROVIDER_COLUMN_MAP(CCustomWindowsFile)
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)
END_PROVIDER_COLUMN_MAP()
};
```

`CCustomWindowsFile` 호출 되는 [사용자 레코드 클래스](../../data/oledb/user-record.md) 공급자의 행 집합의 열을 설명 하는 맵도 있기 때문입니다. 공급자 열 지도 PROVIDER_COLUMN_ENTRY 매크로 사용 하 여 행 집합의 각 필드에 대해 하나의 항목을 포함 합니다. 매크로 열 이름, 서 수 및 항목을 구조에 오프셋을 지정합니다. 위의 코드에서 공급자 열 항목에 오프셋을 포함 합니다 `WIN32_FIND_DATA` 구조입니다. 소비자가 호출 하는 경우 `IRowset::GetData`, 하나의 연속 된 버퍼에서 데이터를 전송 합니다. 포인터 산술 연산을 수행 하면 작업을 수행 하는 대신 지도 사용 하면 데이터 멤버를 지정할 수 있습니다.

`CCustomRowset` 클래스도 포함 된 `Execute` 메서드. `Execute` 네이티브 소스에서 데이터를 실제로 읽고 무엇 이며 다음 코드에서는 마법사에서 생성 된 `Execute` 메서드. 함수는 Win32를 사용 `FindFirstFile` 하 고 `FindNextFile` 디렉터리의 파일에 대 한 정보를 검색 한 인스턴스의에 배치 하는 Api는 `CCustomWindowsFile` 클래스입니다.

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H

HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)
{
   USES_CONVERSION;
   BOOL bFound = FALSE;
   HANDLE hFile;
   LPTSTR  szDir = (m_strCommandText == _T("")) ? _T("*.*") :
       OLE2T(m_strCommandText);
   CCustomWindowsFile wf;
   hFile = FindFirstFile(szDir, &wf);
   if (hFile == INVALID_HANDLE_VALUE)
      return DB_E_ERRORSINCOMMAND;
   LONG cFiles = 1;
   BOOL bMoreFiles = TRUE;
   while (bMoreFiles)
   {
      if (!m_rgRowData.Add(wf))
         return E_OUTOFMEMORY;
      bMoreFiles = FindNextFile(hFile, &wf);
      cFiles++;
   }
   FindClose(hFile);
   if (pcRowsAffected != NULL)
      *pcRowsAffected = cFiles;
   return S_OK;
}
```

검색할 디렉터리를 표시 `m_strCommandText`; 나타내는 텍스트를 포함 합니다 `ICommandText` 명령 개체의 인터페이스입니다. 디렉터리가 없는 지정 된 경우 현재 디렉터리를 사용 합니다.

메서드 (행에 해당) 각 파일에 대해 하나의 항목을 생성 하 고에 배치 된 `m_rgRowData` 데이터 멤버입니다. 합니다 `CRowsetImpl` 클래스 정의 `m_rgRowData` 데이터 멤버입니다. 이 배열에 있는 데이터 전체 테이블이 표시 되 고 템플릿 전체에서 사용 됩니다.

## <a name="see-also"></a>참고자료

[공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)<br/>
