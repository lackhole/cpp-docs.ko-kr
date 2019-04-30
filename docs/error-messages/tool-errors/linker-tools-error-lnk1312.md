---
title: 링커 도구 오류 LNK1312
ms.date: 11/04/2016
f1_keywords:
- LNK1312
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
ms.openlocfilehash: 49fa7e7963d6bb561e1602b58fe1f26c5f3d54bd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160473"
---
# <a name="linker-tools-error-lnk1312"></a>링커 도구 오류 LNK1312

잘못 되었거나 손상 된 파일: 어셈블리를 가져올 수 없습니다.

어셈블리, 모듈 또는 어셈블리를 사용 하 여 컴파일된 이외의 파일을 빌드하면 **/clr** 에 전달 된 합니다 **/ASSEMBLYMODULE** 링커 옵션.  개체 파일을 전달 하는 경우 **/ASSEMBLYMODULE**만 개체에 직접 전달할을 링커에 대신에 **/ASSEMBLYMODULE**합니다.

## <a name="example"></a>예제

다음 샘플.obj 파일을 생성 합니다.

```
// LNK1312.cpp
// compile with: /clr /LD
public ref class A {
public:
   int i;
};
```

## <a name="example"></a>예제

다음 샘플 LNK1312를 생성합니다.

```
// LNK1312_b.cpp
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj
// LNK1312 error expected
public ref class M {};
```