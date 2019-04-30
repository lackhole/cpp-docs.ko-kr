---
title: 링커 도구 경고 LNK4104
ms.date: 11/04/2016
f1_keywords:
- LNK4104
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
ms.openlocfilehash: 3d89b27c32b33b917abb7fc140eebf5924142423
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298544"
---
# <a name="linker-tools-warning-lnk4104"></a>링커 도구 경고 LNK4104

'symbol' 기호의 내보내기는 PRIVATE 이어야 합니다.

`symbol` 다음 중 하나일 수 있습니다.

- `DllCanUnloadNow`

- `DllGetClassObject`

- `DllGetClassFactoryFromClassString`

- `DllGetDocumentation`

- `DllInitialize`

- `DllInstall`

- `DllRegisterServer`

- `DllRegisterServerEx`

- `DllRegisterServerExW`

- `DllUnload`

- `DllUnregisterServer`

- `RasCustomDeleteEntryNotify`

- `RasCustomDial`

- `RasCustomDialDlg`

- `RasCustomEntryDlg`

이 경고는 DLL에 대 한 가져오기 라이브러리를 빌드할 때 내보내집니다. 및 모듈 정의 파일에 전용으로 지정 하지 않고 위의 함수 중 하나를 내보내기. 일반적으로 이러한 함수는 OLE에 의해서만 사용에 대 한 내보내집니다. 가져오기 라이브러리에 배치할 링크 된 프로그램이 라이브러리를 올바르게 호출 하면 비정상적인 동작이 발생할 수 있습니다. PRIVATE 키워드에 대 한 자세한 내용은 참조 하세요. [내보내기를](../../build/reference/exports.md)합니다.