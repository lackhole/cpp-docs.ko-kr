---
title: CLR 통합(C++/CX)
ms.date: 01/22/2017
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
ms.openlocfilehash: df0c5e9cfaf9a4148c8d16b68ee04b4e9ce82e6a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257779"
---
# <a name="clr-integration-ccx"></a>CLR 통합(C++/CX)

C +에서 특별 한 처리를 수신 하는 일부 Windows 런타임 형식 + CX 및는 CLR (공용 언어 런타임)을 기반으로 하는 언어입니다. 이 문서에서는 한 언어의 여러 형식을 다른 언어에 매핑하는 방법을 설명합니다. 예를 들어 CLR은 Windows.Foundation.IVector를 System.Collections.IList에 매핑하고, Windows.Foundation.IMap를 System.Collections.IDictionary에 매핑합니다. 마찬가지로, C++/CX에는 특별히 platform:: delegate 및 platform:: string과 같은 형식을 매핑합니다.

## <a name="mapping-the-windows-runtime-to-ccx"></a>Windows 런타임 매핑 C++/CX

때 C++/CX Windows 메타 데이터 (.winmd) 파일을 읽고, 컴파일러에서 자동으로 매핑합니다 공통 Windows 런타임 네임 스페이스 하 고 형식을 C++/CX 네임 스페이스 및 형식입니다. 예를 들어 숫자 Windows 런타임 형식 `UInt32` 자동으로 매핑됩니다 `default::uint32`합니다.

C++/CX 다른 여러 Windows 런타임 형식을에 매핑하는 **플랫폼** 네임 스페이스입니다. 예를 들어 합니다 **windows:: foundation** HSTRING 핸들을 나타내는 읽기 전용 유니코드 텍스트 문자열에 매핑되는 C++/CX `Platform::String` 클래스입니다. 매핑되는 Windows 런타임 작업 오류 HRESULT를 반환 하는 경우는 C++/CX `Platform::Exception`합니다.

C++/CX 형식의 기능 향상을 위해 Windows 런타임 네임 스페이스의 특정 형식을 매핑합니다. 이러한 형식에 대 한 C++/CX 도우미 생성자 및 관련 된 메서드를 제공 합니다. C++ 형식의 표준.winmd 파일에서 사용할 수 없는 합니다.

다음 목록에서는 새 생성자 및 도우미 메서드를 지원하는 값 구조체를 보여 줍니다. 구조체 초기화 목록을 사용하는 이전에 작성된 코드가 있으면 새로 추가된 생성자를 사용하도록 이를 변경합니다.

**Windows::Foundation**

- 요소

- Rect

- 크기

**Windows::UI**

- 색

**Windows::UI::Xaml**

- CornerRadius

- 기간

- GridLength

- Thickness

**Windows::UI::Xaml::Interop**

- TypeName

**Windows::UI::Xaml::Media**

- 행렬

**Windows::UI::Xaml::Media::Animation**

- KeyTime

- RepeatBehavior

**Windows::UI::Xaml::Media::Media3D**

- Matrix3D

## <a name="mapping-the-clr-to-ccx"></a>매핑 CLR C++/CX

때 시각적 개체 C++ 또는 C# 컴파일러는.winmd 파일 읽기, 적절 한 메타 데이터 파일의 특정 형식을 자동으로 매핑합니다 C++/CX 또는 CLR 형식입니다. IVector CLR에서 예를 들어\<T > IList 인터페이스는 매핑됩니다\<T >입니다. 하지만 C++/CX는 IVector\<T > 인터페이스는 다른 형식에 매핑되어 있지 않습니다.

IReference\<T >는 Windows 런타임에서 매핑됩니다\<T >.net에서.

## <a name="see-also"></a>참고자료

[다른 언어와의 상호 운용](../cppcx/interoperating-with-other-languages-c-cx.md)
