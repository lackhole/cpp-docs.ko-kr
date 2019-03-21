---
title: /MANIFESTINPUT(매니페스트 입력 지정)
ms.date: 11/04/2016
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
ms.openlocfilehash: bf192664a7a2402b06621167d91dff67ce0741a9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814228"
---
# <a name="manifestinput-specify-manifest-input"></a>/MANIFESTINPUT(매니페스트 입력 지정)

이미지에 포함 된 매니페스트에 포함할 매니페스트 입력된 파일을 지정 합니다.

## <a name="syntax"></a>구문

```
/MANIFESTINPUT:filename
```

### <a name="parameters"></a>매개 변수

*filename*<br/>
포함 된 매니페스트에 포함할 매니페스트 파일입니다.

## <a name="remarks"></a>설명

합니다 **/MANIFESTINPUT** 옵션 실행 가능 이미지에 포함된 된 매니페스트를 만드는 데 사용할 입력된 파일의 경로 지정 합니다. 여러 매니페스트 입력 파일이 여러 번 스위치를 사용 해야 하는 경우, 각 입력된 파일에 한 번씩입니다. 매니페스트 입력된 파일이 포함 된 매니페스트를 만들려면 병합 됩니다. 이 옵션을 사용 합니다 **/매니페스트: 포함할** 옵션입니다.

이 옵션은 Visual Studio에서 직접 설정할 수 없습니다. 대신 사용 합니다 **추가 매니페스트 파일** 포함할 추가 매니페스트 파일을 지정 하려면 프로젝트의 속성입니다. 자세한 내용은 [입력 및 출력, 매니페스트 도구, 구성 속성 \<프로젝트 이름 > 속성 페이지 대화 상자](input-and-output-manifest-tool.md)합니다.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
