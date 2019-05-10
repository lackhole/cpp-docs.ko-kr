---
title: '방법: -Clr 컴파일에 네이티브 형식 사용'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- compilation, native types in /clr
- /clr compiler option [C++], using native types
ms.assetid: 3a505c90-4adb-4942-9cf9-7d1fdcbc01e7
ms.openlocfilehash: 9979113ac4ffc062ddfe8654279af03036984f38
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387203"
---
# <a name="how-to-use-a-native-type-in-a-clr-compilation"></a>방법: /Clr 컴파일에 네이티브 형식 사용

네이티브 형식을 정의할 수 있습니다는 **/clr** 컴파일 및 어셈블리 내에서 해당 네이티브 형식을 사용 하 여 모든 유효 합니다. 그러나 네이티브 형식을 참조 된 메타 데이터에서 사용 하기 위해 제공 됩니다.

각 어셈블리는 사용 하 여 모든 기본 형식의 정의 포함 해야 합니다.

자세한 내용은 [/clr(공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.

## <a name="example"></a>예제

이 샘플에서는 정의 하 고 네이티브 형식을 사용 하는 구성 요소를 만듭니다.

```
// use_native_type_in_clr.cpp
// compile with: /clr /LD
public struct NativeClass {
   static int Test() { return 98; }
};

public ref struct ManagedClass {
   static int i = NativeClass::Test();
   void Test() {
      System::Console::WriteLine(i);
   }
};
```

## <a name="example"></a>예제

이 샘플에서는 구성 요소를 사용 하는 클라이언트를 정의 합니다. 컴파일 대상에 정의 되어 있지 않으면 해당 네이티브 형식에 액세스 하는 오류 인지 확인 합니다.

```
// use_native_type_in_clr_2.cpp
// compile with: /clr
#using "use_native_type_in_clr.dll"
// Uncomment the following 3 lines to resolve.
// public struct NativeClass {
//    static int Test() { return 98; }
// };

int main() {
   ManagedClass x;
   x.Test();

   System::Console::WriteLine(NativeClass::Test());   // C2653
}
```

## <a name="see-also"></a>참고자료

[C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
