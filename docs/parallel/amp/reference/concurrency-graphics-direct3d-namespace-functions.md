---
title: Concurrency::graphics::direct3d 네임 스페이스 함수
ms.date: 11/04/2016
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d::get_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_texture
ms.assetid: 11ee1d42-333e-4ae9-95ac-4cf68c06d13d
ms.openlocfilehash: 18fb409b033ea14c3a140ea6600fc43cf3a8d603
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405549"
---
# <a name="concurrencygraphicsdirect3d-namespace-functions"></a>Concurrency::graphics::direct3d 네임 스페이스 함수

||||
|-|-|-|
|[get_sampler](#get_sampler)|[get_texture](#get_texture)|[make_sampler](#make_sampler)|
|[make_texture](#make_texture)|[msad4](#msad4)|

##  <a name="get_sampler"></a>  get_sampler

지정된 된 샘플러 개체를 나타내는 보기 하는 지정 된 액셀러레이터 키에 D3D 샘플러 상태 인터페이스를 가져옵니다.

```
IUnknown* get_sampler(
    const Concurrency::accelerator_view& _Av,
    const sampler& _Sampler) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Av*<br/>
D3D 샘플러 상태를 만들려는 D3D 액셀러레이터 보기입니다.

*_Sampler*<br/>
기본 D3D 샘플러 상태 인터페이스를 만들어집니다는 샘플러 개체입니다.

### <a name="return-value"></a>반환 값

지정 된 샘플러를 나타내는 D3D 샘플러 상태에 해당 하는 IUnknown 인터페이스 포인터입니다.

##  <a name="get_texture"></a>  get_texture

지정 된 내부 Direct3D 텍스처 인터페이스를 가져옵니다 [질감](texture-class.md) 개체입니다.

```
template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const texture<value_type, _Rank>& _Texture) restrict(cpu);

template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const writeonly_texture_view<value_type, _Rank>& _Texture) restrict(cpu);

template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const texture_view<value_type, _Rank>& _Texture) restrict(cpu);
```

### <a name="parameters"></a>매개 변수

*value_type*<br/>
질감의 요소 형식입니다.

*_Rank*<br/>
질감의 순위입니다.

*_Texture*<br/>
질감 또는 텍스처 보기 기본 Direct3D 질감 인터페이스가 반환 되는 accelerator_view와 연결 합니다.

### <a name="return-value"></a>반환 값

내부 Direct3D 텍스쳐에 해당 하는 IUnknown 인터페이스 포인터입니다.

##  <a name="make_sampler"></a>  make_sampler

D3D 샘플러 상태 인터페이스 포인터에서 샘플러를 만듭니다.

```
sampler make_sampler(_In_ IUnknown* _D3D_sampler) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_D3D_sampler*<br/>
IUnknown 인터페이스 포인터에서 샘플러를 만들려면 D3D 샘플러 상태입니다.

### <a name="return-value"></a>반환 값

샘플러는 제공된 된 D3D 샘플러 상태를 나타냅니다.

##  <a name="make_texture"></a>  make_texture

만듭니다는 [질감](texture-class.md) 지정된 된 매개 변수를 사용 하 여 개체입니다.

```
template<
    typename value_type,
    int _Rank
>
texture<value_type, _Rank> make_texture(
    const Concurrency::accelerator_view& _Av,
    _In_ IUnknown* _D3D_texture,
    DXGI_FORMAT _View_format = DXGI_FORMAT_UNKNOWN) restrict(cpu);
```

### <a name="parameters"></a>매개 변수

*value_type*<br/>
질감의 요소 형식입니다.

*_Rank*<br/>
질감의 순위입니다.

*_Av*<br/>
텍스처를 만들려는 D3D 액셀러레이터 보기입니다.

*_D3D_texture*<br/>
질감을 만드는 데 D3D 질감의 IUnknown 인터페이스 포인터입니다.

*_View_format*<br/>
이 질감에서 만든 보기를 사용 하는 DXGI 형식입니다. 내부 형식 _D3D_texture 및이 템플릿의 value_type 형식을 파생할 DXGI_FORMAT_UNKNOWN (기본값)를 전달 합니다. 제공 된 형식은 _D3D_texture의 내부 형식과 호환 되어야 합니다.

### <a name="return-value"></a>반환 값

제공 된 D3D 텍스처를 사용 하 여 질감입니다.

##  <a name="msad4"></a>  msad4

4 바이트 참조 값 및 8 바이트 소스 값을 비교 하 고 4 개 합계의 벡터를 누적 합니다. 각 합계 참조 값과 소스 값 사이 있는 다른 바이트 정렬의 절대 차이의 마스킹된 합에 해당합니다.

```
inline uint4 msad4(
    uint _Reference,
    uint2 _Source,
    uint4 _Accum) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Reference*<br/>
하나의 uint 값 4 바이트의 배열

*_Source*<br/>
소스 배열에서 두 개의 uint 값의 벡터는 8 바이트입니다.

*_Accum*<br/>
참조 값과 소스 값 사이 서로 다른 바이트 정렬의 절대 차이의 마스킹된 합에 추가 될 4 개의 값의 벡터.

### <a name="return-value"></a>반환 값

4 개 합계의 벡터를 반환 합니다. 각 합계 참조 값과 소스 값 사이 있는 다른 바이트 정렬의 절대 차이의 마스킹된 합에 해당합니다.

## <a name="requirements"></a>요구 사항

**헤더:** amp_graphics.h

**네임스페이스:** Concurrency::graphics::direct3d

## <a name="see-also"></a>참고자료

[Concurrency::graphics::direct3d 네임스페이스](concurrency-graphics-direct3d-namespace.md)
