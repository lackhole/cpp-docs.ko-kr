---
title: 컴파일러 오류 C2268
ms.date: 11/04/2016
f1_keywords:
- C2268
helpviewer_keywords:
- C2268
ms.assetid: 0ed055c9-3c6f-4df2-a5b6-85cf0e01a249
ms.openlocfilehash: 11e0c2c81e9bcd2249321e83a506aeaa832c2ee8
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301797"
---
# <a name="compiler-error-c2268"></a>컴파일러 오류 C2268

'function'은 컴파일러에서 미리 정의한 라이브러리 도우미입니다. /GL 옵션을 지정하면 라이브러리 도우미가 지원되지 않습니다. /GL을 지정하지 않고 개체 파일 'file'을 컴파일하세요.

소스 코드에 정의된 함수가 내부 컴파일러 함수와 이름이 같습니다. [/GL](../../build/reference/gl-whole-program-optimization.md)없이 함수를 포함하는 모듈을 컴파일합니다.

다음 샘플에서는 C2268을 생성합니다.

```c
// C2268.c
// compile with: /c
// processor: x86
extern int SHFusionLoadLibrary(int lpLibFileName);

int __cdecl _except_handler3(void) {
   return SHFusionLoadLibrary(0);
}

extern int main(void);

void* mainCRTStartup(void* p) {
   p = main;
   return p;
}
```

그리고

```c
// C2268b.c
// compile with: C2268.c /EHsc /GL /Ob0 /O2 /Fa /GS- /link /nodefaultlib
// processor: x86
extern int SHFusionLoadLibrary(int lpLibFileName);

extern int __cdecl _except_handler3(void);
extern void mainCRTStartup(void*);
int g = 2;

#define ENTERCONTEXT(fail) \
   int ulCookie = 0;\
   if (!SHActivateContext(&ulCookie)) \
      return fail;\
   __try {

#define LEAVECONTEXT \
    } __finally {SHDeactivateContext(ulCookie);}

int SHActivateContext(int* a) {
    return *a == g || !*a ||_except_handler3();
}

void SHDeactivateContext(int a) {
    g = a;
}

int SHFusionLoadLibrary(int lpLibFileName) {   // C2268
    ENTERCONTEXT(0)
    g = lpLibFileName;
    LEAVECONTEXT

    return lpLibFileName;
}

int main(void) {
    g = SHFusionLoadLibrary(10);
    return 0;
}
```
