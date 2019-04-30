---
title: 정규식(C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- regular expressions [C++]
- .NET Framework [C++], regular expressions
- regular expressions [C++], about regular expressions
- parsing strings [C++]
- examples [C++], strings
- regular expressions [C++], parsing strings
- Split method, parsing strings
- strings [C++], parsing
- substrings, simple matches
- searching, exact substring matches
- strings [C++], exact substring matching
- regular expressions [C++], simple matching
- IsMatch method
- strings [C++], extracting data from
- formatted strings [C++]
- regular expressions [C++], extracting data fields
- data [C++], extracting from strings
- regular expressions [C++], rearranging data
- data [C++], rearranging
- search and replace
- Replace method
- regular expressions [C++], search and replace
- strings [C++], formatting
- data [C++], formatting
- regular expressions [C++], validating data formatting
ms.assetid: 838bab49-0dbc-4089-a604-ef146269ef5a
ms.openlocfilehash: 24a278e4d5b208c5d8e3b95b9f5a0bd0306dbab3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384664"
---
# <a name="regular-expressions-ccli"></a>정규식(C++/CLI)

.NET Framework의 정규식 클래스를 사용 하는 다양 한 문자열 작업을 보여 줍니다.

다음 항목에서는.NET Framework의 사용을 보여 줍니다 <xref:System.Text.RegularExpressions> 네임 스페이스 (및 경우에는 <xref:System.String.Split%2A?displayProperty=fullName> 메서드)를 검색 하려면 구문 분석 및 문자열을 수정 합니다.

## <a name="parse_regex"></a> 정규식을 사용 하 여 문자열 구문 분석

다음 코드 예제에서는 간단한 문자열을 사용 하 여 구문 분석 하는 방법을 보여 줍니다 합니다 <xref:System.Text.RegularExpressions.Regex> 클래스는 <xref:System.Text.RegularExpressions?displayProperty=fullName> 네임 스페이스입니다. 여러 유형의 단어 설명자를 포함 하는 문자열 생성 됩니다. 문자열 구문 분석 되를 사용 하는 <xref:System.Text.RegularExpressions.Regex> 클래스와 함께 <xref:System.Text.RegularExpressions.Match> 클래스입니다. 그런 다음 문장에서 각 단어는 별도로 표시 됩니다.

### <a name="example"></a>예제

```cpp
// regex_parse.cpp
// compile with: /clr
#using <system.dll>

using namespace System;
using namespace System::Text::RegularExpressions;

int main( )
{
   int words = 0;
   String^ pattern = "[a-zA-Z]*";
   Console::WriteLine( "pattern : '{0}'", pattern );
   Regex^ regex = gcnew Regex( pattern );

   String^ line = "one\ttwo three:four,five six  seven";
   Console::WriteLine( "text : '{0}'", line );
   for( Match^ match = regex->Match( line );
        match->Success; match = match->NextMatch( ) )
   {
      if( match->Value->Length > 0 )
      {
         words++;
         Console::WriteLine( "{0}", match->Value );
      }
   }
   Console::WriteLine( "Number of Words : {0}", words );

   return 0;
}
```

## <a name="parse_split"></a> Split 메서드를 사용 하 여 문자열 구문 분석

다음 코드 예제는 <xref:System.String.Split%2A?displayProperty=fullName> 문자열에서 각 단어를 추출 하는 방법입니다. 여러 유형의 단어 설명자를 포함 하는 문자열 생성 되 고 호출 하 여 구문 분석 <xref:System.String.Split%2A> 설명자의 목록을 사용 하 여 합니다. 그런 다음 문장에서 각 단어는 별도로 표시 됩니다.

### <a name="example"></a>예제

```cpp
// regex_split.cpp
// compile with: /clr
using namespace System;

int main()
{
   String^ delimStr = " ,.:\t";
   Console::WriteLine( "delimiter : '{0}'", delimStr );
   array<Char>^ delimiter = delimStr->ToCharArray( );
   array<String^>^ words;
   String^ line = "one\ttwo three:four,five six seven";

   Console::WriteLine( "text : '{0}'", line );
   words = line->Split( delimiter );
   Console::WriteLine( "Number of Words : {0}", words->Length );
   for (int word=0; word<words->Length; word++)
      Console::WriteLine( "{0}", words[word] );

   return 0;
}
```

## <a name="regex_simple"></a> 단순 일치에 정규식 사용

다음 코드 예제는 부분 문자열 정확히 일치 항목을 찾을 정규식을 사용 합니다. 정적 검색 하는지 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> 입력으로 두 문자열을 사용 하는 메서드. 첫 번째 문자열을 검색할 수 이며 두 번째 패턴에 대 한 검색입니다.

### <a name="example"></a>예제

```cpp
// regex_simple.cpp
// compile with: /clr
#using <System.dll>

using namespace System;
using namespace System::Text::RegularExpressions;

int main()
{
   array<String^>^ sentence =
   {
      "cow over the moon",
      "Betsy the Cow",
      "cowering in the corner",
      "no match here"
   };

   String^ matchStr = "cow";
   for (int i=0; i<sentence->Length; i++)
   {
      Console::Write( "{0,24}", sentence[i] );
      if ( Regex::IsMatch( sentence[i], matchStr,
                     RegexOptions::IgnoreCase ) )
         Console::WriteLine("  (match for '{0}' found)", matchStr);
      else
         Console::WriteLine("");
   }
   return 0;
}
```

## <a name="regex_extract"></a> 정규식을 사용 하 여 데이터 필드를 추출 하려면

다음 코드 예제에서는 서식이 지정 된 문자열에서 데이터를 추출 하는 정규식의 사용을 보여 줍니다. 다음 코드 예제에서는 <xref:System.Text.RegularExpressions.Regex> 전자 메일 주소에 해당 하는 패턴을 지정 하는 클래스입니다. 이 패턴이 사용자와 각 전자 메일 주소의 호스트 이름 부분을 검색할 수 있는 필드 식별자를 포함 합니다. <xref:System.Text.RegularExpressions.Match> 클래스 실제 패턴 일치를 수행 하는 데 사용 됩니다. 지정 된 전자 메일 주소를 유효한 경우 사용자 이름 및 호스트 이름을 추출 되 고 표시 합니다.

### <a name="example"></a>예제

```cpp
// Regex_extract.cpp
// compile with: /clr
#using <System.dll>

using namespace System;
using namespace System::Text::RegularExpressions;

int main()
{
    array<String^>^ address=
    {
        "jay@southridgevideo.com",
        "barry@adatum.com",
        "treyresearch.net",
        "karen@proseware.com"
    };

    Regex^ emailregex = gcnew Regex("(?<user>[^@]+)@(?<host>.+)");

    for (int i=0; i<address->Length; i++)
    {
        Match^ m = emailregex->Match( address[i] );
        Console::Write("\n{0,25}", address[i]);

        if ( m->Success )
        {
            Console::Write("   User='{0}'",
            m->Groups["user"]->Value);
            Console::Write("   Host='{0}'",
            m->Groups["host"]->Value);
        }
        else
            Console::Write("   (invalid email address)");
        }

    Console::WriteLine("");
    return 0;
}
```

## <a name="regex_rearrange"></a> 정규식을 사용 하 여 데이터를 다시 정렬 하려면

다음 코드 예제를 다시 정렬 하거나 데이터의 서식을 다시 지정 하는.NET Framework 정규식 지원을 사용할 수 있는 방법을 보여 줍니다. 다음 코드 예제에서는 합니다 <xref:System.Text.RegularExpressions.Regex> 고 <xref:System.Text.RegularExpressions.Match> 첫 번째 이름과 마지막 이름 문자열에서 추출 하 고 그런 다음 이러한 이름 요소를 역순으로 표시 하는 클래스입니다.

<xref:System.Text.RegularExpressions.Regex> 클래스 데이터의 현재 형식에 설명 하는 정규식을 생성 하는 데 사용 됩니다. 두 개의 이름을 쉼표로 구분 된 될 것으로 간주 됩니다 및 모든 양의 콤마 앞뒤에 공백을 사용할 수 있습니다. <xref:System.Text.RegularExpressions.Match> 메서드는 다음 각 문자열을 분석 하는 데 사용 됩니다. 성공 하면 첫 번째 이름과 마지막 이름에서 검색 된 <xref:System.Text.RegularExpressions.Match> 개체를 표시 합니다.

### <a name="example"></a>예제

```cpp
// regex_reorder.cpp
// compile with: /clr
#using <System.dll>
using namespace System;
using namespace Text::RegularExpressions;

int main()
{
   array<String^>^ name =
   {
      "Abolrous, Sam",
      "Berg,Matt",
      "Berry , Jo",
      "www.contoso.com"
   };

   Regex^ reg = gcnew Regex("(?<last>\\w*)\\s*,\\s*(?<first>\\w*)");

   for ( int i=0; i < name->Length; i++ )
   {
      Console::Write( "{0,-20}", name[i] );
      Match^ m = reg->Match( name[i] );
      if ( m->Success )
      {
         String^ first = m->Groups["first"]->Value;
         String^ last = m->Groups["last"]->Value;
         Console::WriteLine("{0} {1}", first, last);
      }
      else
         Console::WriteLine("(invalid)");
   }
   return 0;
}
```

## <a name="regex_search"></a> 찾기 및 바꾸기에 정규식을 사용 합니다.

다음 코드 예제에서는 어떻게 정규식 클래스 <xref:System.Text.RegularExpressions.Regex> 찾기 및 바꾸기 수행 하기 위해 사용할 수 있습니다. 사용 하 여 <xref:System.Text.RegularExpressions.Regex.Replace%2A> 메서드. 두 문자열을 입력으로 사용 되는 버전: 수정할 문자열과 (있는 경우) 섹션 대신 삽입할 문자열에 지정 된 패턴과 일치 하는 <xref:System.Text.RegularExpressions.Regex> 개체.

이 코드는 밑줄 (_)를 사용 하 여 문자열의 모든 숫자를 대체 하 고 효과적으로 제거 하는 빈 문자열을 가진 다음으로 바꿉니다. 동일한 효과 한 번에 수행할 수 있습니다 하지만 두 단계는 여기 데모 용도로 사용 됩니다.

### <a name="example"></a>예제

```cpp
// regex_replace.cpp
// compile with: /clr
#using <System.dll>
using namespace System::Text::RegularExpressions;
using namespace System;

int main()
{
   String^ before = "The q43uick bro254wn f0ox ju4mped";
   Console::WriteLine("original  : {0}", before);

   Regex^ digitRegex = gcnew Regex("(?<digit>[0-9])");
   String^ after = digitRegex->Replace(before, "_");
   Console::WriteLine("1st regex : {0}", after);

   Regex^ underbarRegex = gcnew Regex("_");
   String^ after2 = underbarRegex->Replace(after, "");
   Console::WriteLine("2nd regex : {0}", after2);

   return 0;
}
```

## <a name="regex_validate"></a> 데이터 형식 유효성 검사에 정규식을 사용 합니다.

다음 코드 예제에서는 정규식을 문자열의 서식을 확인을 사용 하는 방법을 보여 줍니다. 다음 코드 예제에서는 문자열 올바른 전화 번호를 포함 해야 합니다. 다음 코드 예제에서는 문자열 "\d{3}-\d{3}-\d{4}" 각 필드는 올바른 전화 번호를 나타내기 위해. 문자열에 "d" 숫자를 나타내며 각 "d" 뒤에 있는 인수 반드시 필요한 자릿수를 나타냅니다. 이 경우에 번호가 대시로 구분할 필요 합니다.

### <a name="example"></a>예제

```cpp
// regex_validate.cpp
// compile with: /clr
#using <System.dll>

using namespace System;
using namespace Text::RegularExpressions;

int main()
{
   array<String^>^ number =
   {
      "123-456-7890",
      "444-234-22450",
      "690-203-6578",
      "146-893-232",
      "146-839-2322",
      "4007-295-1111",
      "407-295-1111",
      "407-2-5555",
   };

   String^ regStr = "^\\d{3}-\\d{3}-\\d{4}$";

   for ( int i = 0; i < number->Length; i++ )
   {
      Console::Write( "{0,14}", number[i] );

      if ( Regex::IsMatch( number[i], regStr ) )
         Console::WriteLine(" - valid");
      else
         Console::WriteLine(" - invalid");
   }
   return 0;
}
```

## <a name="related-sections"></a>관련 단원

[.NET Framework 정규식](/dotnet/standard/base-types/regular-expressions)

## <a name="see-also"></a>참고자료

[C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
