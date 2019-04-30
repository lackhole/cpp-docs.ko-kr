---
title: 선언 및 정의 (C++)
ms.date: 11/04/2016
ms.assetid: 678f1424-e12f-45e0-a957-8169e5fef6cb
ms.openlocfilehash: 1e76f636a6efd652ac629ad2f97f0b09f6171f9c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399072"
---
# <a name="declarations-and-definitions-c"></a>선언 및 정의 (C++)

선언은 프로그램에서 하는 이름, 변수, 네임 스페이스, 함수 및 클래스의 이름 예입니다. 또한, 선언은 형식 정보뿐만 아니라 선언되는 개체의 다른 특성도 지정합니다. 이름은 먼저 선언해야 사용할 수 있습니다. C++에서는 이름이 선언되는 지점에 따라 이름이 컴파일러에 표시되는지 여부가 달라집니다. 함수 또는 컴파일 단위의; 나중에 선언 된 클래스를 참조할 수 없습니다. 사용할 수 있습니다 *정방향 선언* 이 제한을 해결 하려면.

정의는 이름을 설명 하는 코드 또는 데이터를 지정 합니다. 선언할 항목을 위한 저장소 공간을 할당하려면 컴파일러에 정의가 있어야 합니다.

## <a name="declarations"></a>선언

선언은 프로그램에 하나 이상의 이름을 제공합니다. 선언은 프로그램에서 두 번 이상 발생할 수 있습니다. 따라서 클래스, 구조체, 열거 형식 및 다른 사용자 정의 형식이 각 컴파일 단위에 대해 선언될 수 있습니다. 이 여러 선언에 대한 제약 조건은 모든 선언이 동일해야 한다는 것입니다. 다음 경우를 제외하고 선언은 정의 역할도 합니다.

1. 선언이 함수 프로토타입(함수 본문이 없는 함수 선언)입니다.

1. 포함 된 **extern** 지정자 하지만 이니셜라이저 (개체 및 변수) 또는 함수 본문 (함수). 이것은 정의가 반드시 현재 변환 단위에 있지 않으며 이름 외부 링크를 제공해 줌을 나타냅니다.

1. 선언이 클래스 선언 내의 정적 데이터 멤버입니다.

   정적 클래스 데이터 멤버는 클래스의 모든 개체가 공유하는 개별 변수이므로 클래스 선언 외부에서 정의 및 초기화되어야 합니다. (클래스 및 클래스 멤버에 대 한 자세한 내용은 참조 하세요. [클래스](../cpp/classes-and-structs-cpp.md).)

1. 선언이 `class T;`과 같은 정의가 뒤따르지 않는 클래스 이름 선언입니다.

1. **typedef** 문입니다.

다음은 정의이기도 한 선언의 예제입니다.

```cpp
// Declare and define int variables i and j.
int i;
int j = 10;

// Declare enumeration suits.
enum suits { Spades = 1, Clubs, Hearts, Diamonds };

// Declare class CheckBox.
class CheckBox : public Control
{
public:
            Boolean IsChecked();
    virtual int     ChangeState() = 0;
};
```

정의가 아닌 일부 선언은 다음과 같습니다.

```cpp
extern int i;
char *strchr( const char *Str, const char Target );
```

선언자 바로 뒤, 이니셜라이저 앞(선택 사항)에서 이름이 선언된다고 간주합니다. 자세한 내용은 [선언 지점](../cpp/point-of-declaration-in-cpp.md)합니다.

선언에서 발생 한 *범위*합니다. 범위는 선언된 이름의 표시 및 정의된 개체(있는 경우)의 기간을 제어합니다. 범위 규칙이 선언 상호 작용 하는 방법에 대 한 자세한 내용은 참조 하세요. [범위](../cpp/scope-visual-cpp.md)합니다.

개체 선언 이기도 정의가 포함 되어 있지 않으면 합니다 **extern** 에 설명 된 저장소 클래스 지정자 [저장소 클래스](storage-classes-cpp.md)합니다. 함수 선언도 프로토타입이 아니라면 정의입니다. 프로토타입은 정의 함수 본문이 없는 함수 헤더입니다. 개체 정의를 통해 해당 개체에 대해 저장소가 할당되고 적절한 초기화가 수행됩니다.

## <a name="definitions"></a>정의

정의는 개체 또는 변수, 함수, 클래스 또는 열거자의 고유 사양입니다. 정의가 고유해야 하기 때문에 프로그램에는 지정된 프로그램 요소에 대한 정의가 하나만 포함될 수 있습니다. 선언과 정의 간에 다 대 일 대응이 있을 수 있습니다. 프로그램 요소가 선언되지만 정의되지는 않는 두 가지 경우가 있습니다.

1. 함수가 선언되지만 함수 호출 또는 함수의 주소를 사용하는 식으로 참조되지 않습니다.

1. 클래스가 정의가 알려질 필요가 없는 방식으로만 사용됩니다. 그러나 클래스는 선언되어야 합니다. 다음 코드에서는 이러한 경우를 보여 줍니다.

    ```cpp
    // definitions.cpp
    class WindowCounter;   // Forward declaration; no definition

    class Window
    {
       // Definition of WindowCounter not required
       static WindowCounter windowCounter;
    };

    int main()
    {
    }
    ```

## <a name="see-also"></a>참고자료

[기본 개념](../cpp/basic-concepts-cpp.md)<br/>
[선언 지점](../cpp/point-of-declaration-in-cpp.md)