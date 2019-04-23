---
title: OLE DB 공급자에 문자열 저장
ms.date: 10/26/2018
helpviewer_keywords:
- user records, editing
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
ms.openlocfilehash: 5dce7dac84ef69da17baac135a68bd78698c4456
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026411"
---
# <a name="storing-strings-in-the-ole-db-provider"></a>OLE DB 공급자에 문자열 저장

*사용자 지정*RS.h, 합니다 **ATL OLE DB 공급자 마법사** 호출 하는 기본 사용자 레코드를 만듭니다 `CWindowsFile`합니다. 두 문자열을 처리 하려면 수정할 `CWindowsFile` 다음 코드 에서처럼:

```cpp
////////////////////////////////////////////////////////////////////////
class CCustomWindowsFile:
   public WIN32_FIND_DATA
{
public:
DWORD dwBookmark;
static const int iSize = 256;    // Add this
TCHAR szCommand[iSize];          // Add this
TCHAR szText[iSize];             // Add this
TCHAR szCommand2[iSize];         // Add this
TCHAR szText2[iSize];            // Add this

BEGIN_PROVIDER_COLUMN_MAP(CCustomWindowsFile)
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)

   PROVIDER_COLUMN_ENTRY_STR("Command", 6, szCommand)    // Add this
   PROVIDER_COLUMN_ENTRY_STR("Text", 7, szText)          // Add this
   PROVIDER_COLUMN_ENTRY_STR("Command2", 8, szCommand2)  // Add this
   PROVIDER_COLUMN_ENTRY_STR("Text2", 9, szText2)        // Add this
END_PROVIDER_COLUMN_MAP()

   bool operator==(const CCustomWindowsFile& am) // This is optional
   {
      return (lstrcmpi(cFileName, am.cFileName) == 0);
   }
};
```

데이터 멤버 `szCommand` 하 고 `szText` 사용 하 여 두 문자열을 나타내는 `szCommand2` 및 `szText2` 필요한 경우 추가 열을 사용 하 여 합니다. 데이터 멤버 `dwBookmark` 이 단순한 읽기 전용 공급자에 필요 하지 않습니다 하지만 나중에 추가 하는 데 사용 되는 `IRowsetLocate` 인터페이스를 참조 하세요 [단순한 읽기 전용 공급자의 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)합니다. `==` 인스턴스를 비교 하는 연산자 (이 연산자 구현은 선택 사항).

이 작업을 하는 경우에의 기능을 추가할 수 있습니다 [OLE DB 공급자로 문자열 읽어들이기](../../data/oledb/reading-strings-into-the-ole-db-provider.md)합니다.

## <a name="see-also"></a>참고자료

[단순한 읽기 전용 공급자 구현](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>
