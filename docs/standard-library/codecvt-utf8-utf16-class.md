---
title: codecvt_utf8_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::cvt_utf8_utf16
helpviewer_keywords:
- codecvt_utf8_utf16 class
ms.assetid: 4c12c881-5dba-4e39-b338-0b9caff5af29
ms.openlocfilehash: 42c9c8643edc795748c1f12c5180471f281c4142
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405263"
---
# <a name="codecvtutf8utf16"></a>codecvt_utf8_utf16

UTF-16으로 인코드된 와이드 문자와 UTF-8로 인코드된 바이트 스트림 간에 변환되는 [로캘](../standard-library/locale-class.md) 패싯을 나타냅니다.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8_utf16 : public _STD codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>매개 변수

*Elem*<br/>
와이드 문자 요소 형식입니다.

*Maxcode*<br/>
로캘 패싯에 대한 최대 문자 수입니다.

*모드*<br/>
로캘 패싯에 대한 구성 정보입니다.

## <a name="remarks"></a>설명

바이트 스트림은 이진 파일 또는 텍스트 파일에 작성할 수 있습니다.

## <a name="requirements"></a>요구 사항

헤더: \<codecvt >

Namespace: std
