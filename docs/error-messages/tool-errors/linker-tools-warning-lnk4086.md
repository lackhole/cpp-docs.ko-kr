---
title: 링커 도구 경고 LNK4086
ms.date: 11/04/2016
f1_keywords:
- LNK4086
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
ms.openlocfilehash: c6a5a0714e070e6cf3aee8efcdfbdfa07fa9ee69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399937"
---
# <a name="linker-tools-warning-lnk4086"></a>링커 도구 경고 LNK4086

entrypoint 'function' 'number' 바이트 인수가 있는 __stdcall이 아닙니다. 이미지를 실행할 수 없습니다.

Dll 진입점 이어야 `__stdcall`합니다. 사용 하 여 함수를 다시 컴파일 중 하나는 [/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md) 옵션 또는 지정 `__stdcall` 또는 WINAPI 함수를 정의 하는 경우.