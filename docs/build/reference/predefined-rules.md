---
title: 미리 정의된 규칙
ms.date: 11/04/2016
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
ms.openlocfilehash: 7a922a239306f10121791caa8f9f088cea88c019
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827332"
---
# <a name="predefined-rules"></a>미리 정의된 규칙

NMAKE 제공한 명령 및 옵션 매크로 사용 하는 미리 정의 된 규칙입니다.

|규칙|명령|기본<br /><br /> action|Batch<br /><br /> 규칙|실행 되는 플랫폼 nmake|
|----------|-------------|------------------------|--------------------|----------------------------|
|.asm.exe|$(AS) $(AFLAGS) $<|ml $<|아니요|x86|
|.asm.obj|$(AS) $(AFLAGS) /c $<|ml /c $<|예|x86|
|.asm.exe|$(AS) $(AFLAGS) $<|ml64 $<|아니요|X64|
|.asm.obj|$(AS) $(AFLAGS) /c $<|ml64 /c $<|예|X64|
|.c.exe|$(CC) $(CFLAGS) $<|cl $<|아니요|모두|
|.c.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|예|모두|
|.cc.exe|$(CC) $(CFLAGS) $<|cl $<|아니요|모두|
|.cc.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|예|모두|
|.cpp.exe|$(CPP) $(CPPFLAGS) $<|cl $<|아니요|모두|
|.cpp.obj|$(CPP) $(CPPFLAGS) /c $<|cl /c $<|예|모두|
|.cxx.exe|$(CXX) $(CXXFLAGS) $<|cl $<|아니요|모두|
|.cxx.obj|$(CXX) $(CXXFLAGS) /c $<|cl /c $<|예|모두|
|.rc.res|$(RC) $(RFLAGS) /r $<|rc /r $<|아니요|모두|

## <a name="see-also"></a>참고자료

[유추 규칙](inference-rules.md)
