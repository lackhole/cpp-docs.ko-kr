---
title: 읽기 전용 공급자 테스트
ms.date: 11/04/2016
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, calling
- OLE DB providers, testing
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
ms.openlocfilehash: a9601b2afe40133a5cc88589b530b5ed549ac81e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025132"
---
# <a name="testing-the-read-only-provider"></a>읽기 전용 공급자 테스트

공급자를 테스트 하려면 소비자가 있어야 합니다. 공급자를 사용 하 여 소비자과 일치할 수 있으면 도움이 됩니다. OLE DB 소비자 템플릿은 OLE DB에 대 한 씬 래퍼 되며 공급자 COM 개체와 일치 합니다. 원본 소비자 템플릿을 사용 하 여 운송 되 면 때문에 디버그 하는 공급자를 쉽습니다. 소비자 템플릿은 또한 소비자 응용 프로그램을 개발 하는 매우 작고 빠른 방법입니다.

이 항목의 예제 테스트 소비자에 대 한 기본 MFC 응용 프로그램 마법사 응용 프로그램을 만듭니다. 테스트 응용 프로그램을 추가 하는 OLE DB 소비자 템플릿 코드를 사용 하 여 간단한입니다.

## <a name="to-create-the-test-application"></a>테스트 응용 프로그램을 만들려면

1. **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.

1. 에 **프로젝트 형식** 창을 **설치 됨** > **시각적 C++**   >  **MFC/ATL** 폴더 . 에 **템플릿을** 창 **MFC 응용 프로그램**합니다.

1. 프로젝트 이름을 입력 *TestProv*를 클릭 하 고 **확인**합니다.

   합니다 **MFC 응용 프로그램** 마법사가 나타납니다.

1. 에 **응용 프로그램 종류** 페이지에서 **대화 상자 기반**입니다.

1. 에 **고급 기능** 페이지에서 **Automation**를 클릭 하 고 **마침**합니다.

> [!NOTE]
> 추가 하는 경우 응용 프로그램 자동화 지원이 필요 하지 않습니다 `CoInitialize` 에서 `CTestProvApp::InitInstance`합니다.

확인 및 편집할 수는 **TestProv** 에서 선택 하 여 대화 상자 (IDD_TESTPROV_DIALOG) **리소스 뷰**합니다. 대화 상자에서 행 집합의 각 문자열에 대해 하나씩 두 개의 목록 상자를 배치 합니다. 키를 눌러 목록 상자 둘 다에 대 한 정렬 속성을 해제 **Alt**+**Enter** 목록 상자를 선택 하면 설정 된 **정렬** 속성**False**합니다. 또한 배치는 **실행** 가져올 파일 대화 상자에서 단추입니다. 완성 된 **TestProv** 대화 상자는 각각 "String 1" 및 "2 String" 레이블이 지정 된 두 개의 목록 상자 있어야; 있습니다 **확인**합니다 **취소**, 및 **실행**  단추입니다.

(이 경우 TestProvDlg.h)에서 대화 상자 클래스에 대 한 헤더 파일을 엽니다. 클래스 선언) (외부 헤더 파일에 다음 코드를 추가 합니다.

```cpp
////////////////////////////////////////////////////////////////////////
// TestProvDlg.h
#include <atldbcli.h>  

class CProvider
{
// Attributes
public:
   char   szField1[16];
   char   szField2[16];

   // Binding Maps
BEGIN_COLUMN_MAP(CProvider)
   COLUMN_ENTRY(1, szField1)
   COLUMN_ENTRY(2, szField2)
END_COLUMN_MAP()
};
```

코드에는 행 집합의 수 하는 열을 정의 하는 사용자 레코드를 나타냅니다. 클라이언트 호출 하는 경우 `IAccessor::CreateAccessor`, 이러한 항목을 사용 하 여 바인딩할 열을 지정 합니다. OLE DB 소비자 템플릿은 열을 동적으로 바인딩할 수 있습니다. COLUMN_ENTRY 매크로 PROVIDER_COLUMN_ENTRY 매크로의 클라이언트 쪽 버전입니다. 두 COLUMN_ENTRY 매크로 서 수, 두 문자열에 대 한 형식, 길이 및 데이터 멤버를 지정합니다.

처리기 함수를 추가 합니다 **실행** 단추를 눌러 **Ctrl** 을 두 번 클릭 합니다 **실행** 단추. 함수에 다음 코드를 추가 합니다.

```cpp
///////////////////////////////////////////////////////////////////////
// TestProvDlg.cpp

void CTestProvDlg::OnRun()
{
   CCommand<CAccessor<CProvider>> table;
   CDataSource source;
   CSession session;

   if (source.Open("Custom.Custom.1", NULL) != S_OK)
      return;

   if (session.Open(source) != S_OK)
      return;

   if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)
      return;

   while (table.MoveNext() == S_OK)
   {
      m_ctlString1.AddString(table.szField1);
      m_ctlString2.AddString(table.szField2);
   }
}
```

합니다 `CCommand`, `CDataSource`, 및 `CSession` OLE DB 소비자 템플릿에 속하는 모든 클래스입니다. 각 클래스는 공급자에서 COM 개체를 모방합니다. 합니다 `CCommand` 개체는 `CProvider` 템플릿 매개 변수로 헤더 파일에 선언 된 클래스입니다. `CProvider` 매개 변수는 공급자에서 데이터에 액세스 하는 데 사용할 수 있는 바인딩을 나타냅니다. 

열려는 클래스의 각 줄은 공급자의 각 COM 개체를 만듭니다. 사용 하 여 공급자를 찾으려면는 `ProgID` 공급자입니다. 가져올 수 있습니다는 `ProgID` Custom.rgs 파일을 확인 하거나 시스템 레지스트리에서 (공급자의 디렉터리를 열고 검색할는 `ProgID` 키).

MyData.txt 파일이 포함 된 `MyProv` 샘플입니다. 파일을 직접 사용 하 여 편집기를 만들고 입력 문자열에서 키를 눌러 수가 짝수인 **Enter** 각 문자열 사이입니다. 파일을 이동 하는 경우 경로 이름을 변경 합니다.

문자열에 전달 "c:\\\samples\\\myprov\\\MyData.txt"에 `table.Open` 줄. 경우에 `Open` 호출 표시 하려면이 문자열은 전달 하는 `SetCommandText` 공급자의 메서드. `ICommandText::Execute` 메서드는 문자열을 사용 합니다.

데이터를 페치 하려면 호출 `MoveNext` 테이블에 있습니다. `MoveNext` 호출 된 `IRowset::GetNextRows`, `GetRowCount`, 및 `GetData` 함수입니다. 더 많은 행이 없는 경우 (즉, 행 집합의 현재 위치 보다 큽니다 `GetRowCount`), 루프가 종료 됩니다.

행이 더 이상 경우 공급자 DB_S_ENDOFROWSET를 반환 합니다. DB_S_ENDOFROWSET 값 오류가 아닙니다. 데이터 인출 루프를 취소 하지 SUCCEEDED 매크로 사용 하는 S_OK에 대해 항상 확인 해야 합니다.

이제을 빌드 및 프로그램을 테스트할 수 있어야 합니다.

## <a name="see-also"></a>참고자료

[단순한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)