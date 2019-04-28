---
title: ADO.NET을 사용하여 데이터 액세스(C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- ADO.NET [C++]
- .NET Framework [C++], data access
- databases [C++], accessing in C++
- data access [C++], ADO.NET
- data [C++], ADO.NET
- native strings [C++]
- ADO.NET [C++], marshaling ANSI strings
- strings [C++], ADO.NET
- BSTRs, strings
- ADO.NET [C++], marshaling BSTR strings
- strings [C++], marshaling BSTR strings
- ADO.NET [C++], marshaling Unicode strings
- Unicode [C++], strings
- strings [C++], Unicode
- VARIANT, marshaling
- ADO.NET [C++], marshaling VARIANT types
- VARIANT
- SAFEARRAY, marshaling
- ADO.NET [C++], marshaling SAFEARRAY types
ms.assetid: b0cd987d-1ea7-4f76-ba01-cbd52503d06d
ms.openlocfilehash: b258e574b912b1c32e5ffae7ba29cfc5f9903685
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209094"
---
# <a name="data-access-using-adonet-ccli"></a>ADO.NET을 사용하여 데이터 액세스(C++/CLI)

ADO.NET은 데이터 액세스를 위한.NET Framework API 및 기능과 이전 데이터 액세스 솔루션에서 일치 하지 않는 사용 편의성을 제공 합니다. 이 섹션에서는 몇 가지 고유한 visual ADO.NET 관련 문제를 설명 C++ 네이티브 형식을 마샬링하 같이 사용자입니다.

ADO.NET에서 언어 런타임 (CLR (공용)를 실행합니다. 따라서 ADO.NET을 사용 하 여 상호 작용 하는 모든 응용 프로그램은 CLR을 대상도 해야 합니다. 그러나 의미는 아닙니다는 네이티브 응용 프로그램 ADO.NET을 사용할 수 없습니다. 이 예제에서는 네이티브 코드에서 ADO.NET 데이터베이스와 상호 작용 하는 방법을 보여 줍니다.

## <a name="marshal_ansi"></a> ADO.NET 용 ANSI 문자열 마샬링

기본 문자열을 추가 하는 방법을 보여 줍니다 (`char *`) 데이터베이스를 마샬링하는 방법을 <xref:System.String?displayProperty=fullName> 네이티브 문자열에 데이터베이스에서.

### <a name="example"></a>예제

이 예제에서는 클래스 DatabaseClass 만들어집니다 ADO.NET을 사용 하 여 상호 작용 하도록 <xref:System.Data.DataTable> 개체입니다. 이 클래스는 네이티브 C++ `class` (비교 했을 때를 `ref class` 하거나 `value class`). 이 네이티브 코드에서이 클래스를 사용 하려고 하 고 네이티브 코드에서 관리 되는 형식을 사용할 수 없습니다 때문에 필요. 이 클래스는 표시 된 대로 CLR을 대상으로 컴파일될는 `#pragma managed` 클래스 선언 앞에 지시문입니다. 이 지시문에 대 한 자세한 내용은 참조 하세요. [관리 되는, 관리 되지 않는](../preprocessor/managed-unmanaged.md)합니다.

DatabaseClass 클래스의 private 멤버를 확인 합니다. `gcroot<DataTable ^> table`합니다. 네이티브 형식에는 관리 되는 형식이 포함 될 수 없습니다는 `gcroot` 키워드는 필요 합니다. 에 대 한 자세한 `gcroot`를 참조 하세요 [방법: 네이티브 형식으로 핸들 선언](../dotnet/how-to-declare-handles-in-native-types.md)합니다.

이 예제의 코드의 나머지 부분은 네이티브 C++ 코드를으로 표시 됩니다는 `#pragma unmanaged` 지시문 앞 `main`합니다. 이 예제에서는에서는 DatabaseClass의 새 인스턴스를 만들고 테이블을 만들고 테이블에 일부 행을 입력 하는 메서드를 호출 합니다. 해당 네이티브 확인 C++ 문자열 StringCol 데이터베이스 열에 대 한 값으로 전달 합니다. Databaseclass 내에서 이러한 문자열의 마샬링 기능을 사용 하 여 관리 되는 문자열 마샬링되는 <xref:System.Runtime.InteropServices?displayProperty=fullName> 네임 스페이스입니다. 메서드 특히, <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> 마샬링하는 데 사용 되는 `char *` 를 <xref:System.String>, 및 메서드 <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> 마샬링하는 데 사용 됩니다는 <xref:System.String> 를 `char *`.

> [!NOTE]
>  할당 한 메모리가 <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> 중 하나를 호출 하 여 할당을 취소 해야 합니다 <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> 또는 `GlobalFree`합니다.

```cpp
// adonet_marshal_string_native.cpp
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll
#include <comdef.h>
#include <gcroot.h>
#include <iostream>
using namespace std;

#using <System.Data.dll>
using namespace System;
using namespace System::Data;
using namespace System::Runtime::InteropServices;

#define MAXCOLS 100

#pragma managed
class DatabaseClass
{
public:
    DatabaseClass() : table(nullptr) { }

    void AddRow(char *stringColValue)
    {
        // Add a row to the table.
        DataRow ^row = table->NewRow();
        row["StringCol"] = Marshal::PtrToStringAnsi(
            (IntPtr)stringColValue);
        table->Rows->Add(row);
    }

    void CreateAndPopulateTable()
    {
        // Create a simple DataTable.
        table = gcnew DataTable("SampleTable");

        // Add a column of type String to the table.
        DataColumn ^column1 = gcnew DataColumn("StringCol",
            Type::GetType("System.String"));
        table->Columns->Add(column1);
    }

    int GetValuesForColumn(char *dataColumn, char **values,
        int valuesLength)
    {
        // Marshal the name of the column to a managed
        // String.
        String ^columnStr = Marshal::PtrToStringAnsi(
                (IntPtr)dataColumn);

        // Get all rows in the table.
        array<DataRow ^> ^rows = table->Select();
        int len = rows->Length;
        len = (len > valuesLength) ? valuesLength : len;
        for (int i = 0; i < len; i++)
        {
            // Marshal each column value from a managed string
            // to a char *.
            values[i] = (char *)Marshal::StringToHGlobalAnsi(
                (String ^)rows[i][columnStr]).ToPointer();
        }

        return len;
    }

private:
    // Using gcroot, you can use a managed type in
    // a native class.
    gcroot<DataTable ^> table;
};

#pragma unmanaged
int main()
{
    // Create a table and add a few rows to it.
    DatabaseClass *db = new DatabaseClass();
    db->CreateAndPopulateTable();
    db->AddRow("This is string 1.");
    db->AddRow("This is string 2.");

    // Now retrieve the rows and display their contents.
    char *values[MAXCOLS];
    int len = db->GetValuesForColumn(
        "StringCol", values, MAXCOLS);
    for (int i = 0; i < len; i++)
    {
        cout << "StringCol: " << values[i] << endl;

        // Deallocate the memory allocated using
        // Marshal::StringToHGlobalAnsi.
        GlobalFree(values[i]);
    }

    delete db;

    return 0;
}
```

```Output
StringCol: This is string 1.
StringCol: This is string 2.
```

### <a name="compiling-the-code"></a>코드 컴파일

- 명령줄에서 코드를 컴파일하려면 adonet_marshal_string_native.cpp 라는 파일에 코드 예제를 저장 하 고 다음 문을 입력 합니다.

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal_bstr"></a> ADO.NET 용 BSTR 문자열 마샬링

COM 문자열을 추가 하는 방법을 보여 줍니다 (`BSTR`) 데이터베이스를 마샬링하는 방법을 <xref:System.String?displayProperty=fullName> 데이터베이스에서는 `BSTR`합니다.

### <a name="example"></a>예제

이 예제에서는 클래스 DatabaseClass 만들어집니다 ADO.NET을 사용 하 여 상호 작용 하도록 <xref:System.Data.DataTable> 개체입니다. 이 클래스는 네이티브 C++ `class` (비교 했을 때를 `ref class` 하거나 `value class`). 이 네이티브 코드에서이 클래스를 사용 하려고 하 고 네이티브 코드에서 관리 되는 형식을 사용할 수 없습니다 때문에 필요. 이 클래스는 표시 된 대로 CLR을 대상으로 컴파일될는 `#pragma managed` 클래스 선언 앞에 지시문입니다. 이 지시문에 대 한 자세한 내용은 참조 하세요. [관리 되는, 관리 되지 않는](../preprocessor/managed-unmanaged.md)합니다.

DatabaseClass 클래스의 private 멤버를 확인 합니다. `gcroot<DataTable ^> table`합니다. 네이티브 형식에는 관리 되는 형식이 포함 될 수 없습니다는 `gcroot` 키워드는 필요 합니다. 에 대 한 자세한 `gcroot`를 참조 하세요 [방법: 네이티브 형식으로 핸들 선언](../dotnet/how-to-declare-handles-in-native-types.md)합니다.

이 예제의 코드의 나머지 부분은 네이티브 C++ 코드를으로 표시 됩니다는 `#pragma unmanaged` 지시문 앞 `main`합니다. 이 예제에서는에서는 DatabaseClass의 새 인스턴스를 만들고 테이블을 만들고 테이블에 일부 행을 입력 하는 메서드를 호출 합니다. COM 문자열 StringCol 데이터베이스 열에 대 한 값으로 전달 되는 참고 합니다. Databaseclass 내에서 이러한 문자열의 마샬링 기능을 사용 하 여 관리 되는 문자열 마샬링되는 <xref:System.Runtime.InteropServices?displayProperty=fullName> 네임 스페이스입니다. 메서드 특히, <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> 마샬링하는 데 사용 되는 `BSTR` 를 <xref:System.String>, 및 메서드 <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> 마샬링하는 데 사용 됩니다는 <xref:System.String> 를 `BSTR`.

> [!NOTE]
>  할당 한 메모리가 <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> 중 하나를 호출 하 여 할당을 취소 해야 합니다 <xref:System.Runtime.InteropServices.Marshal.FreeBSTR%2A> 또는 `SysFreeString`합니다.

``` cpp
// adonet_marshal_string_bstr.cpp
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll
#include <comdef.h>
#include <gcroot.h>
#include <iostream>
using namespace std;

#using <System.Data.dll>
using namespace System;
using namespace System::Data;
using namespace System::Runtime::InteropServices;

#define MAXCOLS 100

#pragma managed
class DatabaseClass
{
public:
    DatabaseClass() : table(nullptr) { }

    void AddRow(BSTR stringColValue)
    {
        // Add a row to the table.
        DataRow ^row = table->NewRow();
        row["StringCol"] = Marshal::PtrToStringBSTR(
            (IntPtr)stringColValue);
        table->Rows->Add(row);
    }

    void CreateAndPopulateTable()
    {
        // Create a simple DataTable.
        table = gcnew DataTable("SampleTable");

        // Add a column of type String to the table.
        DataColumn ^column1 = gcnew DataColumn("StringCol",
            Type::GetType("System.String"));
        table->Columns->Add(column1);
    }

    int GetValuesForColumn(BSTR dataColumn, BSTR *values,
        int valuesLength)
    {
        // Marshal the name of the column to a managed
        // String.
        String ^columnStr = Marshal::PtrToStringBSTR(
                (IntPtr)dataColumn);

        // Get all rows in the table.
        array<DataRow ^> ^rows = table->Select();
        int len = rows->Length;
        len = (len > valuesLength) ? valuesLength : len;
        for (int i = 0; i < len; i++)
        {
            // Marshal each column value from a managed string
            // to a BSTR.
            values[i] = (BSTR)Marshal::StringToBSTR(
                (String ^)rows[i][columnStr]).ToPointer();
        }

        return len;
    }

private:
    // Using gcroot, you can use a managed type in
    // a native class.
    gcroot<DataTable ^> table;
};

#pragma unmanaged
int main()
{
    // Create a table and add a few rows to it.
    DatabaseClass *db = new DatabaseClass();
    db->CreateAndPopulateTable();

    BSTR str1 = SysAllocString(L"This is string 1.");
    db->AddRow(str1);

    BSTR str2 = SysAllocString(L"This is string 2.");
    db->AddRow(str2);

    // Now retrieve the rows and display their contents.
    BSTR values[MAXCOLS];
    BSTR str3 = SysAllocString(L"StringCol");
    int len = db->GetValuesForColumn(
        str3, values, MAXCOLS);
    for (int i = 0; i < len; i++)
    {
        wcout << "StringCol: " << values[i] << endl;

        // Deallocate the memory allocated using
        // Marshal::StringToBSTR.
        SysFreeString(values[i]);
    }

    SysFreeString(str1);
    SysFreeString(str2);
    SysFreeString(str3);
    delete db;

    return 0;
}
```

```Output
StringCol: This is string 1.
StringCol: This is string 2.
```

### <a name="compiling-the-code"></a>코드 컴파일

- 명령줄에서 코드를 컴파일하려면 adonet_marshal_string_native.cpp 라는 파일에 코드 예제를 저장 하 고 다음 문을 입력 합니다.

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal_unicode"></a> ADO.NET 용 유니코드 문자열 마샬링

네이티브 유니코드 문자열을 추가 하는 방법을 보여 줍니다 (`wchar_t *`)는 데이터베이스를 마샬링하는 방법을 <xref:System.String?displayProperty=fullName> 네이티브 유니코드 문자열에 데이터베이스에서.

### <a name="example"></a>예제

이 예제에서는 클래스 DatabaseClass 만들어집니다 ADO.NET을 사용 하 여 상호 작용 하도록 <xref:System.Data.DataTable> 개체입니다. 이 클래스는 네이티브 C++ `class` (비교 했을 때를 `ref class` 하거나 `value class`). 이 네이티브 코드에서이 클래스를 사용 하려고 하 고 네이티브 코드에서 관리 되는 형식을 사용할 수 없습니다 때문에 필요. 이 클래스는 표시 된 대로 CLR을 대상으로 컴파일될는 `#pragma managed` 클래스 선언 앞에 지시문입니다. 이 지시문에 대 한 자세한 내용은 참조 하세요. [관리 되는, 관리 되지 않는](../preprocessor/managed-unmanaged.md)합니다.

DatabaseClass 클래스의 private 멤버를 확인 합니다. `gcroot<DataTable ^> table`합니다. 네이티브 형식에는 관리 되는 형식이 포함 될 수 없습니다는 `gcroot` 키워드는 필요 합니다. 에 대 한 자세한 `gcroot`를 참조 하세요 [방법: 네이티브 형식으로 핸들 선언](../dotnet/how-to-declare-handles-in-native-types.md)합니다.

이 예제의 코드의 나머지 부분은 네이티브 C++ 코드를으로 표시 됩니다는 `#pragma unmanaged` 지시문 앞 `main`합니다. 이 예제에서는에서는 DatabaseClass의 새 인스턴스를 만들고 테이블을 만들고 테이블에 일부 행을 입력 하는 메서드를 호출 합니다. 참고는 유니코드 C++ 문자열 StringCol 데이터베이스 열에 대 한 값으로 전달 합니다. Databaseclass 내에서 이러한 문자열의 마샬링 기능을 사용 하 여 관리 되는 문자열 마샬링되는 <xref:System.Runtime.InteropServices?displayProperty=fullName> 네임 스페이스입니다. 메서드 특히, <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> 마샬링하는 데 사용 되는 `wchar_t *` 를 <xref:System.String>, 및 메서드 <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> 마샬링하는 데 사용 됩니다는 <xref:System.String> 를 `wchar_t *`.

> [!NOTE]
>  할당 한 메모리가 <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> 중 하나를 호출 하 여 할당을 취소 해야 합니다 <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> 또는 `GlobalFree`합니다.

```cpp
// adonet_marshal_string_wide.cpp
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll
#include <comdef.h>
#include <gcroot.h>
#include <iostream>
using namespace std;

#using <System.Data.dll>
using namespace System;
using namespace System::Data;
using namespace System::Runtime::InteropServices;

#define MAXCOLS 100

#pragma managed
class DatabaseClass
{
public:
    DatabaseClass() : table(nullptr) { }

    void AddRow(wchar_t *stringColValue)
    {
        // Add a row to the table.
        DataRow ^row = table->NewRow();
        row["StringCol"] = Marshal::PtrToStringUni(
            (IntPtr)stringColValue);
        table->Rows->Add(row);
    }

    void CreateAndPopulateTable()
    {
        // Create a simple DataTable.
        table = gcnew DataTable("SampleTable");

        // Add a column of type String to the table.
        DataColumn ^column1 = gcnew DataColumn("StringCol",
            Type::GetType("System.String"));
        table->Columns->Add(column1);
    }

    int GetValuesForColumn(wchar_t *dataColumn, wchar_t **values,
        int valuesLength)
    {
        // Marshal the name of the column to a managed
        // String.
        String ^columnStr = Marshal::PtrToStringUni(
                (IntPtr)dataColumn);

        // Get all rows in the table.
        array<DataRow ^> ^rows = table->Select();
        int len = rows->Length;
        len = (len > valuesLength) ? valuesLength : len;
        for (int i = 0; i < len; i++)
        {
            // Marshal each column value from a managed string
            // to a wchar_t *.
            values[i] = (wchar_t *)Marshal::StringToHGlobalUni(
                (String ^)rows[i][columnStr]).ToPointer();
        }

        return len;
    }

private:
    // Using gcroot, you can use a managed type in
    // a native class.
    gcroot<DataTable ^> table;
};

#pragma unmanaged
int main()
{
    // Create a table and add a few rows to it.
    DatabaseClass *db = new DatabaseClass();
    db->CreateAndPopulateTable();
    db->AddRow(L"This is string 1.");
    db->AddRow(L"This is string 2.");

    // Now retrieve the rows and display their contents.
    wchar_t *values[MAXCOLS];
    int len = db->GetValuesForColumn(
        L"StringCol", values, MAXCOLS);
    for (int i = 0; i < len; i++)
    {
        wcout << "StringCol: " << values[i] << endl;

        // Deallocate the memory allocated using
        // Marshal::StringToHGlobalUni.
        GlobalFree(values[i]);
    }

    delete db;

    return 0;
}
```

```Output
StringCol: This is string 1.
StringCol: This is string 2.
```

### <a name="compiling-the-code"></a>코드 컴파일

- 명령줄에서 코드를 컴파일하려면 adonet_marshal_string_wide.cpp 라는 파일에 코드 예제를 저장 하 고 다음 문을 입력 합니다.

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_wide.cpp
    ```

## <a name="marshal_variant"></a> ADO.NET 용 VARIANT 마샬링

네이티브를 추가 하는 방법을 보여 줍니다 `VARIANT` 데이터베이스를 마샬링하는 방법을 <xref:System.Object?displayProperty=fullName> 네이티브 데이터베이스에서 `VARIANT`합니다.

### <a name="example"></a>예제

이 예제에서는 클래스 DatabaseClass 만들어집니다 ADO.NET을 사용 하 여 상호 작용 하도록 <xref:System.Data.DataTable> 개체입니다. 이 클래스는 네이티브 C++ `class` (비교 했을 때를 `ref class` 하거나 `value class`). 이 네이티브 코드에서이 클래스를 사용 하려고 하 고 네이티브 코드에서 관리 되는 형식을 사용할 수 없습니다 때문에 필요. 이 클래스는 표시 된 대로 CLR을 대상으로 컴파일될는 `#pragma managed` 클래스 선언 앞에 지시문입니다. 이 지시문에 대 한 자세한 내용은 참조 하세요. [관리 되는, 관리 되지 않는](../preprocessor/managed-unmanaged.md)합니다.

DatabaseClass 클래스의 private 멤버를 확인 합니다. `gcroot<DataTable ^> table`합니다. 네이티브 형식에는 관리 되는 형식이 포함 될 수 없습니다는 `gcroot` 키워드는 필요 합니다. 에 대 한 자세한 `gcroot`를 참조 하세요 [방법: 네이티브 형식으로 핸들 선언](../dotnet/how-to-declare-handles-in-native-types.md)합니다.

이 예제의 코드의 나머지 부분은 네이티브 C++ 코드를으로 표시 됩니다는 `#pragma unmanaged` 지시문 앞 `main`합니다. 이 예제에서는에서는 DatabaseClass의 새 인스턴스를 만들고 테이블을 만들고 테이블에 일부 행을 입력 하는 메서드를 호출 합니다. 해당 네이티브 참고 `VARIANT` 형식 ObjectCol 데이터베이스 열에 대 한 값으로 전달 되는 합니다. Databaseclass 내에서 이러한 `VARIANT` 형식은 관리 되는 개체의 마샬링 기능을 사용 하 여 마샬링됩니다는 <xref:System.Runtime.InteropServices?displayProperty=fullName> 네임 스페이스입니다. 메서드 특히, <xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A> 마샬링하는 데 사용 되는 `VARIANT` 에 <xref:System.Object>, 및 메서드 <xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A> 마샬링하는 데 사용 됩니다는 <xref:System.Object> 를 `VARIANT`.

```cpp
// adonet_marshal_variant.cpp
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll
#include <comdef.h>
#include <gcroot.h>
#include <iostream>
using namespace std;

#using <System.Data.dll>
using namespace System;
using namespace System::Data;
using namespace System::Runtime::InteropServices;

#define MAXCOLS 100

#pragma managed
class DatabaseClass
{
public:
    DatabaseClass() : table(nullptr) { }

    void AddRow(VARIANT *objectColValue)
    {
        // Add a row to the table.
        DataRow ^row = table->NewRow();
        row["ObjectCol"] = Marshal::GetObjectForNativeVariant(
            IntPtr(objectColValue));
        table->Rows->Add(row);
    }

    void CreateAndPopulateTable()
    {
        // Create a simple DataTable.
        table = gcnew DataTable("SampleTable");

        // Add a column of type String to the table.
        DataColumn ^column1 = gcnew DataColumn("ObjectCol",
            Type::GetType("System.Object"));
        table->Columns->Add(column1);
    }

    int GetValuesForColumn(wchar_t *dataColumn, VARIANT *values,
        int valuesLength)
    {
        // Marshal the name of the column to a managed
        // String.
        String ^columnStr = Marshal::PtrToStringUni(
                (IntPtr)dataColumn);

        // Get all rows in the table.
        array<DataRow ^> ^rows = table->Select();
        int len = rows->Length;
        len = (len > valuesLength) ? valuesLength : len;
        for (int i = 0; i < len; i++)
        {
            // Marshal each column value from a managed object
            // to a VARIANT.
            Marshal::GetNativeVariantForObject(
                rows[i][columnStr], IntPtr(&values[i]));
        }

        return len;
    }

private:
    // Using gcroot, you can use a managed type in
    // a native class.
    gcroot<DataTable ^> table;
};

#pragma unmanaged
int main()
{
    // Create a table and add a few rows to it.
    DatabaseClass *db = new DatabaseClass();
    db->CreateAndPopulateTable();

    BSTR bstr1 = SysAllocString(L"This is a BSTR in a VARIANT.");
    VARIANT v1;
    v1.vt = VT_BSTR;
    v1.bstrVal = bstr1;
    db->AddRow(&v1);

    int i = 42;
    VARIANT v2;
    v2.vt = VT_I4;
    v2.lVal = i;
    db->AddRow(&v2);

    // Now retrieve the rows and display their contents.
    VARIANT values[MAXCOLS];
    int len = db->GetValuesForColumn(
        L"ObjectCol", values, MAXCOLS);
    for (int i = 0; i < len; i++)
    {
        switch (values[i].vt)
        {
            case VT_BSTR:
                wcout << L"ObjectCol: " << values[i].bstrVal << endl;
                break;
            case VT_I4:
                cout << "ObjectCol: " << values[i].lVal << endl;
                break;
            default:
                break;
        }

    }

    SysFreeString(bstr1);
    delete db;

    return 0;
}
```

```Output
ObjectCol: This is a BSTR in a VARIANT.
ObjectCol: 42
```

### <a name="compiling-the-code"></a>코드 컴파일

- 명령줄에서 코드를 컴파일하려면 adonet_marshal_variant.cpp 라는 파일에 코드 예제를 저장 하 고 다음 문을 입력 합니다.

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp
    ```

## <a name="marshal_safearray"></a> ADO.NET 용 SAFEARRAY 마샬링

네이티브를 추가 하는 방법을 보여 줍니다 `SAFEARRAY` 데이터베이스를 네이티브 데이터베이스에서 관리 되는 배열을 마샬링하는 방법을 `SAFEARRAY`합니다.

### <a name="example"></a>예제

이 예제에서는 클래스 DatabaseClass 만들어집니다 ADO.NET을 사용 하 여 상호 작용 하도록 <xref:System.Data.DataTable> 개체입니다. 이 클래스는 네이티브 C++ `class` (비교 했을 때를 `ref class` 하거나 `value class`). 이 네이티브 코드에서이 클래스를 사용 하려고 하 고 네이티브 코드에서 관리 되는 형식을 사용할 수 없습니다 때문에 필요. 이 클래스는 표시 된 대로 CLR을 대상으로 컴파일될는 `#pragma managed` 클래스 선언 앞에 지시문입니다. 이 지시문에 대 한 자세한 내용은 참조 하세요. [관리 되는, 관리 되지 않는](../preprocessor/managed-unmanaged.md)합니다.

DatabaseClass 클래스의 private 멤버를 확인 합니다. `gcroot<DataTable ^> table`합니다. 네이티브 형식에는 관리 되는 형식이 포함 될 수 없습니다는 `gcroot` 키워드는 필요 합니다. 에 대 한 자세한 `gcroot`를 참조 하세요 [방법: 네이티브 형식으로 핸들 선언](../dotnet/how-to-declare-handles-in-native-types.md)합니다.

이 예제의 코드의 나머지 부분은 네이티브 C++ 코드를으로 표시 됩니다는 `#pragma unmanaged` 지시문 앞 `main`합니다. 이 예제에서는에서는 DatabaseClass의 새 인스턴스를 만들고 테이블을 만들고 테이블에 일부 행을 입력 하는 메서드를 호출 합니다. 해당 네이티브 참고 `SAFEARRAY` 형식 ArrayIntsCol 데이터베이스 열에 대 한 값으로 전달 되는 합니다. Databaseclass 내에서 이러한 `SAFEARRAY` 형식은 관리 되는 개체의 마샬링 기능을 사용 하 여 마샬링됩니다는 <xref:System.Runtime.InteropServices?displayProperty=fullName> 네임 스페이스입니다. 메서드 특히, <xref:System.Runtime.InteropServices.Marshal.Copy%2A> 마샬링하는 데 사용 되는 `SAFEARRAY` 정수 및 메서드의 관리 되는 배열에 <xref:System.Runtime.InteropServices.Marshal.Copy%2A> 정수의 관리 되는 배열을 마샬링하는 데 사용 되는 `SAFEARRAY`합니다.

```cpp
// adonet_marshal_safearray.cpp
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll
#include <comdef.h>
#include <gcroot.h>
#include <iostream>
using namespace std;

#using <System.Data.dll>
using namespace System;
using namespace System::Data;
using namespace System::Runtime::InteropServices;

#define MAXCOLS 100

#pragma managed
class DatabaseClass
{
public:
    DatabaseClass() : table(nullptr) { }

    void AddRow(SAFEARRAY *arrayIntsColValue)
    {
        // Add a row to the table.
        DataRow ^row = table->NewRow();
        int len = arrayIntsColValue->rgsabound[0].cElements;
        array<int> ^arr = gcnew array<int>(len);

        int *pData;
        SafeArrayAccessData(arrayIntsColValue, (void **)&pData);
        Marshal::Copy(IntPtr(pData), arr, 0, len);
        SafeArrayUnaccessData(arrayIntsColValue);

        row["ArrayIntsCol"] = arr;
        table->Rows->Add(row);
    }

    void CreateAndPopulateTable()
    {
        // Create a simple DataTable.
        table = gcnew DataTable("SampleTable");

        // Add a column of type String to the table.
        DataColumn ^column1 = gcnew DataColumn("ArrayIntsCol",
            Type::GetType("System.Int32[]"));
        table->Columns->Add(column1);
    }

    int GetValuesForColumn(wchar_t *dataColumn, SAFEARRAY **values,
        int valuesLength)
    {
        // Marshal the name of the column to a managed
        // String.
        String ^columnStr = Marshal::PtrToStringUni(
                (IntPtr)dataColumn);

        // Get all rows in the table.
        array<DataRow ^> ^rows = table->Select();
        int len = rows->Length;
        len = (len > valuesLength) ? valuesLength : len;
        for (int i = 0; i < len; i++)
        {
            // Marshal each column value from a managed array
            // of Int32s to a SAFEARRAY of type VT_I4.
            values[i] = SafeArrayCreateVector(VT_I4, 0, 10);
            int *pData;
            SafeArrayAccessData(values[i], (void **)&pData);
            Marshal::Copy((array<int> ^)rows[i][columnStr], 0,
                IntPtr(pData), 10);
            SafeArrayUnaccessData(values[i]);
        }

        return len;
    }

private:
    // Using gcroot, you can use a managed type in
    // a native class.
    gcroot<DataTable ^> table;
};

#pragma unmanaged
int main()
{
    // Create a table and add a few rows to it.
    DatabaseClass *db = new DatabaseClass();
    db->CreateAndPopulateTable();

    // Create a standard array.
    int originalArray[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };

    // Create a SAFEARRAY.
    SAFEARRAY *psa;
    psa = SafeArrayCreateVector(VT_I4, 0, 10);

    // Copy the data from the original array to the SAFEARRAY.
    int *pData;
    HRESULT hr = SafeArrayAccessData(psa, (void **)&pData);
    memcpy(pData, &originalArray, 40);
    SafeArrayUnaccessData(psa);
    db->AddRow(psa);

    // Now retrieve the rows and display their contents.
    SAFEARRAY *values[MAXCOLS];
    int len = db->GetValuesForColumn(
        L"ArrayIntsCol", values, MAXCOLS);
    for (int i = 0; i < len; i++)
    {
        int *pData;
        SafeArrayAccessData(values[i], (void **)&pData);
        for (int j = 0; j < 10; j++)
        {
            cout << pData[j] << " ";
        }
        cout << endl;
        SafeArrayUnaccessData(values[i]);

        // Deallocate the memory allocated using
        // SafeArrayCreateVector.
        SafeArrayDestroy(values[i]);
    }

    SafeArrayDestroy(psa);
    delete db;

    return 0;
}
```

```Output
0 1 2 3 4 5 6 7 8 9
```

### <a name="compiling-the-code"></a>코드 컴파일

- 명령줄에서 코드를 컴파일하려면 adonet_marshal_safearray.cpp 라는 파일에 코드 예제를 저장 하 고 다음 문을 입력 합니다.

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp
    ```

## <a name="net-framework-security"></a>.NET Framework 보안

ADO.NET 관련 보안 문제에 대 한 자세한 내용은 [ADO.NET 응용 프로그램 보안](/dotnet/framework/data/adonet/securing-ado-net-applications)합니다.

## <a name="related-sections"></a>관련 단원

|단원|설명|
|-------------|-----------------|
|[ADO.NET](/dotnet/framework/data/adonet/index)|ADO.NET의.NET 프로그래머에 게 데이터 액세스 서비스를 노출 하는 클래스 집합에 간략하게 설명 합니다.|

## <a name="see-also"></a>참고자료

[C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

[네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)

<xref:System.Runtime.InteropServices>

[상호 운용성](/dotnet/framework/interop/index)
