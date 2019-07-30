---
title: basic_filebuf 클래스
ms.date: 11/04/2016
f1_keywords:
- fstream/std::basic_filebuf
- fstream/std::basic_filebuf::char_type
- fstream/std::basic_filebuf::int_type
- fstream/std::basic_filebuf::off_type
- fstream/std::basic_filebuf::pos_type
- fstream/std::basic_filebuf::traits_type
- fstream/std::basic_filebuf::close
- fstream/std::basic_filebuf::is_open
- fstream/std::basic_filebuf::open
- fstream/std::basic_filebuf::overflow
- fstream/std::basic_filebuf::pbackfail
- fstream/std::basic_filebuf::seekoff
- fstream/std::basic_filebuf::seekpos
- fstream/std::basic_filebuf::setbuf
- fstream/std::basic_filebuf::Swap
- fstream/std::basic_filebuf::sync
- fstream/std::basic_filebuf::uflow
- fstream/std::basic_filebuf::underflow
helpviewer_keywords:
- std::basic_filebuf [C++]
- std::basic_filebuf [C++], char_type
- std::basic_filebuf [C++], int_type
- std::basic_filebuf [C++], off_type
- std::basic_filebuf [C++], pos_type
- std::basic_filebuf [C++], traits_type
- std::basic_filebuf [C++], close
- std::basic_filebuf [C++], is_open
- std::basic_filebuf [C++], open
- std::basic_filebuf [C++], overflow
- std::basic_filebuf [C++], pbackfail
- std::basic_filebuf [C++], seekoff
- std::basic_filebuf [C++], seekpos
- std::basic_filebuf [C++], setbuf
- std::basic_filebuf [C++], Swap
- std::basic_filebuf [C++], sync
- std::basic_filebuf [C++], uflow
- std::basic_filebuf [C++], underflow
ms.assetid: 3196ba5c-bf38-41bd-9a95-70323ddfca1a
ms.openlocfilehash: ae72523c5c0a769a0267da94fead5ea29664276e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459476"
---
# <a name="basicfilebuf-class"></a>basic_filebuf 클래스

외부 파일에 저장 된 요소의 시퀀스에서 문자 특성이 *Tr*클래스에 의해 결정 되는 *Elem*형식 요소의 전송을 제어 하는 스트림 버퍼에 대해 설명 합니다.

## <a name="syntax"></a>구문

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_filebuf : public basic_streambuf<Elem, Tr>
```

### <a name="parameters"></a>매개 변수

*E*\
파일 버퍼의 기본 요소입니다.

*비교한*\
파일 버퍼 기본 요소의 특성(일반적으로 `char_traits`< `Elem`>)입니다.

## <a name="remarks"></a>설명

템플릿 클래스는 외부 파일에 저장된 요소의 시퀀스에서 나가고 들어오는 *Elem* 형식 요소의 전송을 제어하는 스트림 버퍼에 대해 설명하며, 해당 문자 특성은 *Tr* 클래스로 결정됩니다.

> [!NOTE]
> 형식 개체는 형식 매개 변수 *Elem*에 지정 된에 `char *` `char_type` 관계 없이 형식의 내부 버퍼를 사용 하 여 생성 됩니다.`basic_filebuf` 즉, 유니코드 문자열 ( **wchar_t** 문자 포함)은 내부 버퍼에 기록 되기 전에 ANSI 문자열 (문자 **포함)** 로 변환 됩니다. 유니코드 문자열을 버퍼에 저장 하려면 **wchar_t** 형식의 새 버퍼를 만들고 [basic_streambuf::p ubsetbuf](../standard-library/basic-streambuf-class.md#pubsetbuf) `()` 메서드를 사용 하 여 설정 합니다. 이 동작을 보여 주는 예제를 보려면 아래를 참조하세요.

`basic_filebuf`< `Elem`, `Tr`> 클래스의 개체는 열려 있는 파일과 연결된 스트림을 제어하는 `FILE` 개체를 지정하는 파일 포인터를 저장합니다. 또한 보호된 멤버 함수 [overflow](#overflow) 및 [underflow](#underflow)에서 사용하도록 두 가지 파일 변환 패싯에 대한 포인터를 저장합니다. 자세한 내용은 [basic_filebuf::open](#open)을 참조하세요.

## <a name="example"></a>예제

다음 예제에서는 `basic_filebuf<wchar_t>` 형식의 개체가 `pubsetbuf()` 메서드를 호출하여 유니코드 문자열을 내부 버퍼에 강제로 저장하도록 하는 방법을 보여 줍니다.

```cpp
// unicode_basic_filebuf.cpp
// compile with: /EHsc

#include <iostream>
#include <string>
#include <fstream>
#include <iomanip>
#include <memory.h>
#include <string.h>

#define IBUFSIZE 16

using namespace std;

void hexdump(const string& filename);

int main()
{
    wchar_t* wszHello = L"Hello World";
    wchar_t wBuffer[128];

    basic_filebuf<wchar_t> wOutFile;

    // Open a file, wcHello.txt, then write to it, then dump the
    // file's contents in hex
    wOutFile.open("wcHello.txt",
        ios_base::out | ios_base::trunc | ios_base::binary);
    if(!wOutFile.is_open())
    {
        cout << "Error Opening wcHello.txt\n";
        return -1;
    }
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));
    wOutFile.close();
    cout << "Hex Dump of wcHello.txt - note that output is ANSI chars:\n";
    hexdump(string("wcHello.txt"));

    // Open a file, wwHello.txt, then set the internal buffer of
    // the basic_filebuf object to be of type wchar_t, then write
    // to the file and dump the file's contents in hex
    wOutFile.open("wwHello.txt",
        ios_base::out | ios_base::trunc | ios_base::binary);
    if(!wOutFile.is_open())
    {
        cout << "Error Opening wwHello.txt\n";
        return -1;
    }
    wOutFile.pubsetbuf(wBuffer, (streamsize)128);
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));
    wOutFile.close();
    cout << "\nHex Dump of wwHello.txt - note that output is wchar_t chars:\n";
    hexdump(string("wwHello.txt"));

    return 0;
}

// dump contents of filename to stdout in hex
void hexdump(const string& filename)
{
    fstream ifile(filename.c_str(),
        ios_base::in | ios_base::binary);
    char *ibuff = new char[IBUFSIZE];
    char *obuff = new char[(IBUFSIZE*2)+1];
    int i;

    if(!ifile.is_open())
    {
        cout << "Cannot Open " << filename.c_str()
             << " for reading\n";
        return;
    }
    if(!ibuff || !obuff)
    {
        cout << "Cannot Allocate buffers\n";
        ifile.close();
        return;
    }

    while(!ifile.eof())
    {
        memset(obuff,0,(IBUFSIZE*2)+1);
        memset(ibuff,0,IBUFSIZE);
        ifile.read(ibuff,IBUFSIZE);

        // corner case where file is exactly a multiple of
        // 16 bytes in length
        if(ibuff[0] == 0 && ifile.eof())
            break;

        for(i = 0; i < IBUFSIZE; i++)
        {
            if(ibuff[i] >= ' ')
                obuff[i] = ibuff[i];
            else
                obuff[i] = '.';

            cout << setfill('0') << setw(2) << hex
                 << (int)ibuff[i] << ' ';
        }
        cout << "  " << obuff << endl;
    }
    ifile.close();
}
```

```Output
Hex Dump of wcHello.txt - note that output is ANSI chars:
48 65 6c 6c 6f 20 57 6f 72 6c 64 00 00 00 00 00   Hello World.....

Hex Dump of wwHello.txt - note that output is wchar_t chars:
48 00 65 00 6c 00 6c 00 6f 00 20 00 57 00 6f 00   H.e.l.l.o. .W.o.
72 00 6c 00 64 00 00 00 00 00 00 00 00 00 00 00   r.l.d...........
```

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[basic_filebuf](#basic_filebuf)|`basic_filebuf` 형식의 개체를 생성합니다.|

### <a name="typedefs"></a>형식 정의

|형식 이름|설명|
|-|-|
|[char_type](#char_type)|형식 이름을 `Elem` 템플릿 매개 변수와 연결합니다.|
|[int_type](#int_type)|`Tr` 범위에 있는 동일한 이름의 형식에 해당하는 `basic_filebuf`의 범위 내에 이 형식을 만듭니다.|
|[off_type](#off_type)|`Tr` 범위에 있는 동일한 이름의 형식에 해당하는 `basic_filebuf`의 범위 내에 이 형식을 만듭니다.|
|[pos_type](#pos_type)|`Tr` 범위에 있는 동일한 이름의 형식에 해당하는 `basic_filebuf`의 범위 내에 이 형식을 만듭니다.|
|[traits_type](#traits_type)|형식 이름을 `Tr` 템플릿 매개 변수와 연결합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[close](#close)|파일을 닫습니다.|
|[is_open](#is_open)|파일이 열려 있는지 여부를 나타냅니다.|
|[open](#open)|파일을 엽니다.|
|[overflow](#overflow)|가득 찬 버퍼에 새 문자를 삽입할 때 호출할 수 있는 보호된 가상 함수입니다.|
|[pbackfail](#pbackfail)|보호된 가상 멤버 함수는 요소를 입력 스트림에 다시 넣은 후 다음 포인터에서 가리키는 현재 요소로 설정하려고 합니다.|
|[seekoff](#seekoff)|보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.|
|[seekpos](#seekpos)|보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.|
|[setbuf](#setbuf)|보호된 가상 멤버 함수는 파생된 각 스트림 버퍼와 관련된 작업을 수행합니다.|
|[Swap](#swap)|이 `basic_filebuf`의 콘텐츠를 제공된 `basic_filebuf` 매개 변수의 콘텐츠로 교환합니다.|
|[sync](#sync)|보호된 가상 함수는 제어된 스트림을 연결된 외부 스트림과 동기화하려고 합니다.|
|[uflow](../standard-library/basic-streambuf-class.md#uflow)|입력 스트림에서 현재 요소를 추출하는 보호된 가상 함수입니다.|
|[underflow](#underflow)|입력 스트림에서 현재 요소를 추출하는 보호된 가상 함수입니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<fstream>

**네임스페이스:** std

## <a name="basic_filebuf"></a>  basic_filebuf::basic_filebuf

`basic_filebuf` 형식의 개체를 생성합니다.

```cpp
basic_filebuf();

basic_filebuf(basic_filebuf&& right);
```

### <a name="remarks"></a>설명

첫 번째 생성자는 입력 버퍼와 출력 버퍼를 제어하는 모든 포인터에 null 포인터를 저장합니다. 또한 파일 포인터에 null 포인터를 저장합니다.

두 번째 생성자는 rvalue 참조로 처리되는 `right`의 내용으로 개체를 초기화합니다.

## <a name="char_type"></a>  basic_filebuf::char_type

형식 이름을 `Elem` 템플릿 매개 변수와 연결합니다.

```cpp
typedef Elem char_type;
```

## <a name="close"></a>  basic_filebuf::close

파일을 닫습니다.

```cpp
basic_filebuf<Elem, Tr> *close();
```

### <a name="return-value"></a>반환 값

파일 포인터가 null 포인터인 경우 멤버 함수는 null 포인터를 반환합니다.

### <a name="remarks"></a>설명

`close`( `fclose` **fp**)를 호출 합니다. 해당 함수가 0이 아닌 값을 반환하는 경우 이 함수는 null 포인터를 반환합니다. 아닌 경우 **this**를 반환하여 파일을 성공적으로 닫았음을 나타냅니다.

와이드 스트림의 경우 스트림이 열린 이후 또는 `streampos`에 대한 마지막 호출 이후 삽입이 발생하면 함수는 [overflow](#overflow)를 호출합니다. 또한 필요에 따라 호출 `fac` `fac.unshift` 하는 파일 변환 패싯을 사용 하 여 초기 변환 상태를 복원 하는 데 필요한 모든 시퀀스를 삽입 합니다. 따라서 생성 `byte` 된 **char** 형식의 각 요소는 `fputc`( **byte**, **fp**) 형식의 연속 호출로 인해 `fp` 파일 포인터로 지정 된 연결 된 스트림에 기록 됩니다. 또는 쓰기에 대 `fac.unshift` 한 호출이 실패 하면 함수는 성공 하지 않습니다.

### <a name="example"></a>예제

다음 샘플에서는 현재 디렉터리에 두 개의 파일, 즉 basic_filebuf_close.txt(내용: "테스트") 및 iotest.txt(내용: "ssss")가 있다고 가정합니다.

```cpp
// basic_filebuf_close.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main() {
   using namespace std;
   ifstream file;
   basic_ifstream <wchar_t> wfile;
   char c;
   // Open and close with a basic_filebuf
   file.rdbuf()->open( "basic_filebuf_close.txt", ios::in );
   file >> c;
   cout << c << endl;
   file.rdbuf( )->close( );

   // Open/close directly
   file.open( "iotest.txt" );
   file >> c;
   cout << c << endl;
   file.close( );

   // open a file with a wide character name
   wfile.open( L"iotest.txt" );

   // Open and close a nonexistent with a basic_filebuf
   file.rdbuf()->open( "ziotest.txt", ios::in );
   cout << file.fail() << endl;
   file.rdbuf( )->close( );

   // Open/close directly
   file.open( "ziotest.txt" );
   cout << file.fail() << endl;
   file.close( );
}
```

```Output
t
s
0
1
```

## <a name="int_type"></a>  basic_filebuf::int_type

`Tr` 범위에 있는 동일한 이름의 형식에 해당 하는 basic_filebuf's 범위 내에이 형식을 만듭니다.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="is_open"></a>  basic_filebuf::is_open

파일이 열려 있는지 여부를 나타냅니다.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>반환 값

파일 포인터가 null 포인터가 아니면 **true**입니다.

### <a name="example"></a>예제

```cpp
// basic_filebuf_is_open.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main( )
{
   using namespace std;
   ifstream file;
   cout << boolalpha << file.rdbuf( )->is_open( ) << endl;

   file.open( "basic_filebuf_is_open.cpp" );
   cout << file.rdbuf( )->is_open( ) << endl;
}
```

```Output
false
true
```

## <a name="off_type"></a>  basic_filebuf::off_type

`Tr` 범위에 있는 동일한 이름의 형식에 해당 하는 basic_filebuf's 범위 내에이 형식을 만듭니다.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="open"></a>  basic_filebuf::open

파일을 엽니다.

```cpp
basic_filebuf<Elem, Tr> *open(
    const char* _Filename,
    ios_base::openmode _Mode,
    int _Prot = (int)ios_base::_Openprot);

basic_filebuf<Elem, Tr> *open(
    const char* _Filename,
    ios_base::openmode _Mode);

basic_filebuf<Elem, Tr> *open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode,
    int _Prot = (int)ios_base::_Openprot);

basic_filebuf<Elem, Tr> *open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode);
```

### <a name="parameters"></a>매개 변수

*파일 이름 (_s)* \
열어야 할 파일의 이름입니다.

*모드 (_s)* \
[ios_base::openmode](../standard-library/ios-base-class.md#openmode)의 열거형 중 하나입니다.

*_Prot*\
[_Fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)의 *shflag* 매개 변수와 동일한 기본 파일 열기 보호입니다.

### <a name="return-value"></a>반환 값

파일 포인터가 null 포인터인 경우 함수는 null 포인터를 반환합니다. 아닌 경우 **this**를 반환합니다.

### <a name="remarks"></a>설명

멤버 함수는 [fopen](../c-runtime-library/reference/fopen-wfopen.md)( *filename*, **strmode**)을 호출하여 *filename* 파일 이름으로 파일을 엽니다. `strmode`는 **모드 &** ~ ( [ate](../standard-library/ios-base-class.md#openmode) & &#124; [binary](../standard-library/ios-base-class.md#openmode))에서 결정 됩니다.

- `ios_base::in` **"r"** 이 됩니다 (읽기용으로 기존 파일 열기).

- [ios_base::out](../standard-library/ios-base-class.md#fmtflags) 또는 **ios_base::out &#124; ios_base::trunc**는 **"w"** 가 됩니다(기존 파일 자르기 또는 쓰기를 위해 만들기).

- **ios_base::out &#124; app**은 **"a"** 가 됩니다(모든 쓰기를 추가하기 위해 기존 파일 열기).

- **ios_base::in &#124; ios_base::out**은 **"r+"** 가 됩니다(읽기 및 쓰기를 위해 기존 파일 열기).

- **ios_base::in &#124; ios_base::out &#124; ios_base::trunc**는 **"w+"** 가 됩니다(기존 파일 자르기 또는 읽기 및 쓰기를 위해 만들기).

- **ios_base::in &#124; ios_base::out &#124; ios_base::app**은 **"a+"** 가 됩니다(읽기 및 모든 쓰기 추가를 위해 기존 파일 열기).

**Mode & ios_base:: binary** 가 0이 아닌 경우 함수는 `b` 텍스트 `strmode` 스트림이 아닌 이진 스트림을 열기 위해를 추가 합니다. 그런 다음에서 `fopen` 반환 된 값을 파일 포인터 `fp`에 저장 합니다. **mode & ios_base::ate**가 0이 아니고 파일 포인터가 null 포인터가 아니면 함수는 스트림을 파일 끝에 두기 위해 `fseek`( **fp**, 0, `SEEK_END`)를 호출합니다. 해당 위치 지정 작업이 실패 하는 경우 함수 [](#close)는 close `fp`()를 호출 하 고 파일 포인터에 null 포인터를 저장 합니다.

파일 포인터가 null 포인터가 아닌 경우 함수는 파일 변환 패싯을 결정 합니다. `use_facet`< `codecvt`< **Elem**, `char`, **traits_type::** [state_type](../standard-library/char-traits-struct.md#state_type)> > ( [getloc](../standard-library/basic-streambuf-class.md#getloc)) ( [언더플로](#underflow) 및 [오버플로](#overflow)에서 사용)

파일 포인터가 null 포인터인 경우 함수는 null 포인터를 반환합니다. 아닌 경우 **this**를 반환합니다.

### <a name="example"></a>예제

`open`의 사용 예제는 [basic_filebuf::close](#close)를 참조하세요.

## <a name="op_eq"></a>  basic_filebuf::operator=

이 스트림 버퍼 개체의 콘텐츠를 할당합니다. 복사본을 남기지 않는 rvalue와 관련된 이동 할당입니다.

```cpp
basic_filebuf& operator=(basic_filebuf&& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
[basic_filebuf](../standard-library/basic-filebuf-class.md) 개체에 대한 rvalue 참조입니다.

### <a name="return-value"></a>반환 값

*this를 반환합니다.

### <a name="remarks"></a>설명

멤버 연산자는 rvalue 참조로 처리 되는 *오른쪽*의 내용을 사용 하 여 개체의 내용을 바꿉니다. 자세한 내용은 [RValue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 참조하세요.

## <a name="overflow"></a>  basic_filebuf::overflow

가득 찬 버퍼에 새 문자를 삽입할 때 호출됩니다.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>매개 변수

*_Meta*\
버퍼 또는 `traits_type::eof`에 삽입할 문자입니다.

### <a name="return-value"></a>반환 값

함수는 정상적으로 실행되지 않으면 `traits_type::eof`를 반환합니다. 아닌 경우 **traits_type::** [not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*)를 반환합니다.

### <a name="remarks"></a>설명

*_Meta* **! = traits_type::** [eof](../standard-library/char-traits-struct.md#eof)인 경우 보호 된 가상 멤버 함수는 **시도한 요소를**[](../standard-library/char-traits-struct.md#to_char_type)출력 버퍼에 삽입 합니다. 수행할 수 있는 방법은 다양합니다.

- 쓰기 위치가 사용 가능한 경우 요소를 쓰기 위치에 저장하고 출력 버퍼에 대해 다음 포인터를 증분할 수 있습니다.

- 출력 버퍼에 대해 새 스토리지 또는 추가 스토리지를 할당하여 쓰기 위치를 사용 가능하게 만들 수 있습니다.

- 이 메서드는 필요에 따라 호출 `ch` `fac.out` 하는 파일 변환 패싯을 `fac` 사용 하 여 출력 버퍼에서 보류 중인 모든 출력을 변환 하 고 그 다음으로 변환할 수 있습니다. 따라서 생성 `ch` 된 *char* 형식의 각 요소 `fp` 는 파일 포인터로 `fputc`지정 된 연결 된 스트림에 기록 됩니다 ( **ch**, **fp**). 변환 또는 쓰기가 실패하면 함수가 성공하지 못합니다.

## <a name="pbackfail"></a>  basic_filebuf::pbackfail

요소를 입력 스트림에 다시 넣은 후 다음 포인터에서 가리키는 현재 요소로 설정하려고 합니다.

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>매개 변수

*_Meta*\
버퍼에 삽입할 문자 또는 `traits_type::eof`입니다.

### <a name="return-value"></a>반환 값

함수는 정상적으로 실행되지 않으면 `traits_type::eof`를 반환합니다. 그렇지 않으면 **traits_type::** [not_eof](../standard-library/char-traits-struct.md#not_eof)( *\_Meta*)을 반환 합니다.

### <a name="remarks"></a>설명

보호된 가상 멤버 함수는 요소를 입력 버퍼에 다시 넣은 후 다음 포인터에서 가리키는 현재 요소로 설정합니다. *\_Meta* **= = traits_type::** [eof](../standard-library/char-traits-struct.md#eof)인 경우 다시 푸시할 요소는 실제로 현재 요소 이전 스트림에 이미 있는 요소입니다. 그렇지 않으면 해당 요소는 **ch = traits_type::** [to_char_type](../standard-library/char-traits-struct.md#to_char_type)( *\_Meta*)로 바뀝니다. 함수는 여러 가지 방법으로 요소를 다시 넣을 수 있습니다.

- Putback 위치를 사용할 수 있고에 `ch`저장 된 요소가와 비교 되는 경우 입력 버퍼에 대 한 다음 포인터를 감소 시킬 수 있습니다.

- 함수 `putback` 에서 위치를 사용할 수 있는 경우이 작업을 수행할 수 있습니다. 이렇게 하려면 다음 포인터를 해당 위치를 가리키도록 설정 하 `ch` 고 해당 위치에 저장 합니다.

- 함수가 요소를 입력 스트림에 다시 푸시할 수 있는 경우 `ungetc` **char**형식의 요소에 대해를 호출 하는 등의 작업을 수행할 수 있습니다.

## <a name="pos_type"></a>  basic_filebuf::pos_type

`Tr` 범위에 있는 동일한 이름의 형식에 해당 하는 basic_filebuf's 범위 내에이 형식을 만듭니다.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="seekoff"></a>  basic_filebuf::seekoff

제어된 스트림의 현재 위치를 변경하려고 합니다.

```cpp
virtual pos_type seekoff(off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>매개 변수

*_Off*\
을 기준으로 검색할 위치입니다 *(_w)* .

*_ 방식*\
오프셋 작업의 시작 지점입니다. 가능한 값은 [seekdir](../standard-library/ios-base-class.md#seekdir)을 참조하세요.

*(_S)* \
포인터 위치에 대한 모드를 지정합니다. 기본적으로는 읽기 및 쓰기 위치를 수정할 수 있습니다.

### <a name="return-value"></a>반환 값

새 위치 또는 잘못된 스트림 위치를 반환합니다.

### <a name="remarks"></a>설명

보호된 가상 구성원 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다. [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> 클래스 개체의 경우, 와이드 스트림 구문 분석에 필요한 상태 정보 및 오프셋을 저장하는 `fpos_t` 형식의 개체로 스트림 위치를 나타낼 수 있습니다. 오프셋 0은 스트림의 첫 번째 요소를 지정합니다. ([pos_type](../standard-library/basic-streambuf-class.md#pos_type) 형식의 개체는 최소한 `fpos_t` 개체를 저장합니다.)

읽기 및 쓰기용으로 열린 파일의 경우 입력 스트림과 출력 스트림이 나란히 배치됩니다. 삽입과 추출 간에 전환하려면 [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) 또는 [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)를 호출해야 합니다. `pubseekoff`(따라서 `seekoff`)에 대한 호출에는 [텍스트 스트림](../c-runtime-library/text-and-binary-streams.md), [이진 스트림](../c-runtime-library/text-and-binary-streams.md) 및 [와이드 스트림](../c-runtime-library/byte-and-wide-streams.md)에 대한 다양한 제한이 있습니다.

파일 포인터가 `fp` null 포인터인 경우 함수가 실패 합니다. 아닌 경우, 함수는 `fseek`( **fp**, `_Off`, `_Way`)를 호출하여 스트림 위치를 변경하려고 합니다. 해당 함수가 성공 하 고 결과 위치 `fposn` 를 ( **fp**, **& fposn**)을 호출 `fgetpos`하 여 확인할 수 있으면 함수가 성공 합니다. 함수가 성공 하면를 포함 하 `pos_type` `fposn`는 형식의 값을 반환 합니다. 실패하면 잘못된 스트림 위치를 반환합니다.

## <a name="seekpos"></a>  basic_filebuf::seekpos

제어된 스트림의 현재 위치를 변경하려고 합니다.

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>매개 변수

*_Sp*\
찾을 위치입니다.

*(_S)* \
포인터 위치에 대한 모드를 지정합니다. 기본적으로는 읽기 및 쓰기 위치를 수정할 수 있습니다.

### <a name="return-value"></a>반환 값

파일 포인터가 `fp` null 포인터인 경우 함수가 실패 합니다. 그렇지 않으면 시도한 ( **fp**, **& fposn**)를 호출 `fsetpos`하 여 스트림 위치를 변경 합니다. `fposn` 여기서는 `fpos_t` 에 `pos`저장 된 개체입니다. 성공하면 함수는 `pos`을 반환합니다. 실패하면 잘못된 스트림 위치를 반환합니다. 스트림 위치가 잘못되었는지를 확인하려면 반환 값을 `pos_type(off_type(-1))`과 비교합니다.

### <a name="remarks"></a>설명

보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다. [basic_filebuf](../standard-library/basic-filebuf-class.md)\< **Elem**, **Tr**> 클래스 개체의 경우, 와이드 스트림 구문 분석에 필요한 상태 정보 및 오프셋을 저장하는 `fpos_t` 형식의 개체로 스트림 위치를 나타낼 수 있습니다. 오프셋 0은 스트림의 첫 번째 요소를 지정합니다. (`pos_type` 형식의 개체는 최소한 `fpos_t` 개체를 저장합니다.)

읽기 및 쓰기용으로 열린 파일의 경우 입력 스트림과 출력 스트림이 나란히 배치됩니다. 삽입과 추출 간에 전환하려면 [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) 또는 [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)를 호출해야 합니다. `pubseekoff`(따라서 `seekoff`)에 대한 호출에는 텍스트 스트림, 이진 스트림 및 와이드 스트림에 대한 다양한 제한이 있습니다.

와이드 스트림의 경우 스트림이 열린 이후 또는 `streampos`에 대한 마지막 호출 이후 삽입이 발생하면 함수는 [overflow](#overflow)를 호출합니다. 또한 파일 변환 패싯을 `fac` 사용 하 여 필요에 따라 **fac** `.unshift` 를 호출 하 여 초기 변환 상태를 복원 하는 데 필요한 모든 시퀀스를 삽입 합니다. 따라서 생성 `byte` 된 **char** 형식의 각 요소는 `fputc`( **byte**, **fp**) 형식의 연속 호출로 인해 `fp` 파일 포인터로 지정 된 연결 된 스트림에 기록 됩니다. 또는 쓰기에 대 `fac.unshift` 한 호출이 실패 하면 함수는 성공 하지 않습니다.

## <a name="setbuf"></a>  basic_filebuf::setbuf

파생된 각 스트림 버퍼와 관련된 작업을 수행합니다.

```cpp
virtual basic_streambuf<Elem, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>매개 변수

*버퍼 (_m)* \
버퍼에 대한 포인터입니다.

*수*\
버퍼의 크기입니다.

### <a name="return-value"></a>반환 값

`fp` 파일 포인터가 null 포인터인 경우 보호된 멤버 함수는 0을 반환합니다.

### <a name="remarks"></a>설명

`setbuf`는 `setvbuf`(**fp**, (`char`\*) `_Buffer`, `_IOFBF`, `count`\*`sizeof` (**Elem**))을 호출하여 _ *Buffer*에서 시작하는 `count` 요소의 배열을 스트림에 대한 버퍼로 제공합니다. 해당 함수가 0이 아닌 값을 반환하는 경우 이 함수는 null 포인터를 반환합니다. 아닌 경우 성공을 알리기 위해 **this**를 반환합니다.

## <a name="swap"></a>  basic_filebuf::swap

이 `basic_filebuf`의 내용을 제공된 `basic_filebuf`의 내용으로 교환합니다.

```cpp
void swap(basic_filebuf& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
다른 `basic_filebuf`에 대한 `lvalue` 참조입니다.

## <a name="sync"></a>  basic_filebuf::sync

제어된 스트림을 연결된 외부 스트림과 동기화하려고 합니다.

```cpp
virtual int sync();
```

### <a name="return-value"></a>반환 값

파일 포인터가 `fp` null 포인터인 경우 0을 반환 합니다. 아닌 경우, [overflow](#overflow) 및 `fflush`( **fp**)에 대한 호출이 보류 중인 출력을 스트림에 성공적으로 플러시하는 경우에만 0을 반환합니다.

## <a name="traits_type"></a>  basic_filebuf::traits_type

형식 이름을 `Tr` 템플릿 매개 변수와 연결합니다.

```cpp
typedef Tr traits_type;
```

## <a name="underflow"></a>  basic_filebuf::underflow

입력 스트림에서 현재 요소를 추출합니다.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>반환 값

성공하지 못할 경우 함수는 **traits_type::** [eof](../standard-library/char-traits-struct.md#eof)를 반환합니다. 그렇지 않으면 설명 섹션 `ch`에 설명 된 대로 변환 된을 반환 합니다.

### <a name="remarks"></a>설명

보호 된 가상 멤버 함수 시도한는 입력 스트림에서 현재 요소 `ch` 를 추출 하 고 **traits_type::** [to_int_type](../standard-library/char-traits-struct.md#to_int_type)(`ch`)로 요소를 반환 합니다. 수행할 수 있는 방법은 다양합니다.

- 읽기 위치를 사용할 수 있는 경우 읽기 위치 `ch` 에 저장 된 요소로를 사용 하 고 입력 버퍼에 대 한 다음 포인터를 앞으로 이동 합니다.

- `fgetc`(**Fp**) 형식의 연속 호출에서와 같이 **char**형식의 요소를 하나 이상 읽고 파일 변환 패싯 fac를 사용 하 여 필요에 따라 호출 `fac.in` 하는 형식의 `Elem` **ch** 요소로 변환할 수 있습니다. 읽기 또는 변환이 실패하면 함수가 성공하지 못합니다.

## <a name="see-also"></a>참고자료

[\<fstream>](../standard-library/fstream.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream 프로그래밍](../standard-library/iostream-programming.md)\
[iostreams 규칙](../standard-library/iostreams-conventions.md)
