---
title: UICheckState 열거형
ms.date: 04/03/2017
f1_keywords:
- afxwinforms/uicheckstate
helpviewer_keywords:
- uicheckstate enumeration [MFC]
ms.assetid: 2ac0098c-20e7-410c-9685-5ead5cb02b63
ms.openlocfilehash: 1411e9b7cb088c063e17cc7c59871e5f0b83ad9c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309800"
---
# <a name="uicheckstate-enumeration"></a>UICheckState 열거형

명령에 대 한 사용자 인터페이스 항목의 선택 상태를 설명합니다.

### <a name="syntax"></a>구문

```
public enum class
{
   [DefaultValue(typeid<Microsoft::VisualC::MFC::UICheckState>, "Checked")]
   Unchecked,
   Checked,
   Indeterminate
};
```

### <a name="remarks"></a>설명

[ICommandUI::Check](icommandui-interface.md#check) 이러한 값을 사용 하 여 사용자 인터페이스 항목의 상태를 설명 합니다.
Windows Forms를 사용 하 여 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxwinforms.h (atlmfc\lib\mfcmifc80.dll 어셈블리에에서 정의 됨)
