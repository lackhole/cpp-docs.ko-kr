---
title: 타일 사용
ms.date: 11/19/2018
ms.assetid: acb86a86-2b7f-43f1-8fcf-bcc79b21d9a8
ms.openlocfilehash: ede62c80a83b5f5fc1d691bf52dde67140e68246
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405383"
---
# <a name="using-tiles"></a>타일 사용

앱의 가속을 최대화할 바둑판식 배열을 사용할 수 있습니다. 바둑판식 배열 동일한 사각형 하위 집합으로 스레드를 분할 하거나 *타일*합니다. 적절 한 타일 크기와 바둑판식된 알고리즘을 사용 하는 경우에에서 더 많은 가속을 얻을 수 있습니다 프로그램 C++ AMP 코드입니다. 바둑판식 배열의 기본 구성 요소는:

- `tile_static` 변수입니다. 바둑판식 배열의 가장 큰 이점은 통한 성능 향상은 `tile_static` 액세스 합니다. 데이터에 액세스 `tile_static` 메모리 전역 공간에서 데이터 액세스 보다 상당히 빠를 수 있습니다 (`array` 또는 `array_view` 개체). 인스턴스의 `tile_static` 변수 각 타일에 대해 생성 되 고 타일에 있는 모든 스레드가 변수에 액세스할 수 있습니다. 일반적인 바둑판식된 알고리즘에서 데이터에 복사 됩니다 `tile_static` 전역 메모리에서 메모리에서 여러 차례 액세스 하 고는 `tile_static` 메모리입니다.

- [tile_barrier:: wait 메서드](reference/tile-barrier-class.md#wait)합니다. 에 대 한 호출 `tile_barrier::wait` 의 모든 스레드에서 같은 타일에 대 한 호출에 도달할 때까지 현재 스레드의 실행을 일시 중단 `tile_barrier::wait`합니다. 만 실행 하는 타일의 스레드가 호출 이전 스레드가 실행 되는 순서를 보장할 수 없습니다 `tile_barrier::wait` 호출에 도달 했습니다. 모든 스레드가 될 때까지 합니다. 사용 하 여 즉는 `tile_barrier::wait` 메서드를 스레드에서 스레드 기반이 아니라 타일에서 타일 기준으로 작업을 수행할 수 있습니다. 일반적인 바둑판식 알고리즘을 초기화 하는 코드에는 `tile_static` 에 대 한 호출 뒤에 전체 타일에 대 한 메모리 `tile_barrer::wait`합니다. 코드 뒤에 오는 `tile_barrier::wait` 모두에 대 한 액세스를 필요로 하는 계산이 포함 된 `tile_static` 값.

- 로컬 및 전역 인덱싱입니다. 전체 상대적인 스레드 인덱스에 액세스할 수 있습니다 `array_view` 또는 `array` 개체 및 타일에 상대적인 인덱스입니다. 로컬 인덱스를 사용 하 여 코드를 읽고 디버깅 쉽게 만들 수입니다. 일반적으로 액세스 하기 위해 로컬 인덱싱을 사용 하면 `tile_static` 변수 및 액세스 하기 위해 전역 인덱싱을 `array` 고 `array_view` 변수입니다.

- [tiled_extent 클래스](../../parallel/amp/reference/tiled-extent-class.md) 하 고 [tiled_index 클래스](../../parallel/amp/reference/tiled-index-class.md)합니다. 사용할를 `tiled_extent` 대신 개체를 `extent` 개체는 `parallel_for_each` 호출 합니다. 사용할를 `tiled_index` 대신 개체를 `index` 개체는 `parallel_for_each` 호출 합니다.

바둑판식 배열을 활용 하려면 알고리즘 계산 도메인을 타일로 분할 하며 타일 데이터를 복사 `tile_static` 빠른 액세스에 대 한 변수입니다.

## <a name="example-of-global-tile-and-local-indices"></a>예제에서는 전역, 타일 및 로컬 인덱스

다음 다이어그램은 2x3 타일에 있는 데이터는 8x9 매트릭스를 나타냅니다.

![8&#45;에서&#45;9 8x9 매트릭스를 2&#45;에서&#45;3 타일](../../parallel/amp/media/usingtilesmatrix.png "8&#45;에서&#45;9 8x9 매트릭스를 2&#45;에서&#45;3 타일")

다음 예제에서는 전역, 타일을 표시 하 고 바둑판식 매트릭스의 로컬 인덱스 키를 누릅니다. `array_view` 형식의 요소를 사용 하 여 개체를 만들 `Description`합니다. `Description` 보유 전역, 타일 및 행렬에 있는 요소의 로컬 인덱스입니다. 에 대 한 호출의 코드 `parallel_for_each` 값 전역, 타일 및 각 요소의 로컬 인덱스를 설정 합니다. 출력에서 값을 표시 합니다 `Description` 구조입니다.

```cpp
#include <iostream>
#include <iomanip>
#include <Windows.h>
#include <amp.h>
using namespace concurrency;

const int ROWS = 8;
const int COLS = 9;

// tileRow and tileColumn specify the tile that each thread is in.
// globalRow and globalColumn specify the location of the thread in the array_view.
// localRow and localColumn specify the location of the thread relative to the tile.
struct Description {
    int value;
    int tileRow;
    int tileColumn;
    int globalRow;
    int globalColumn;
    int localRow;
    int localColumn;
};

// A helper function for formatting the output.
void SetConsoleColor(int color) {
    int colorValue = (color == 0)  4 : 2;
    SetConsoleTextAttribute(GetStdHandle(STD_OUTPUT_HANDLE), colorValue);
}

// A helper function for formatting the output.
void SetConsoleSize(int height, int width) {
    COORD coord;

    coord.X = width;
    coord.Y = height;
    SetConsoleScreenBufferSize(GetStdHandle(STD_OUTPUT_HANDLE), coord);

    SMALL_RECT* rect = new SMALL_RECT();
    rect->Left = 0;
    rect->Top = 0;
    rect->Right = width;
    rect->Bottom = height;
    SetConsoleWindowInfo(GetStdHandle(STD_OUTPUT_HANDLE), true, rect);
}

// This method creates an 8x9 matrix of Description structures.
// In the call to parallel_for_each, the structure is updated
// with tile, global, and local indices.
void TilingDescription() {
    // Create 72 (8x9) Description structures.
    std::vector<Description> descs;
    for (int i = 0; i < ROWS * COLS; i++) {
        Description d = {i, 0, 0, 0, 0, 0, 0};
        descs.push_back(d);
    }

    // Create an array_view from the Description structures.
    extent<2> matrix(ROWS, COLS);
    array_view<Description, 2> descriptions(matrix, descs);

    // Update each Description with the tile, global, and local indices.
    parallel_for_each(descriptions.extent.tile< 2, 3>(),
        [=] (tiled_index< 2, 3> t_idx) restrict(amp)
    {
        descriptions[t_idx].globalRow = t_idx.global[0];
        descriptions[t_idx].globalColumn = t_idx.global[1];
        descriptions[t_idx].tileRow = t_idx.tile[0];
        descriptions[t_idx].tileColumn = t_idx.tile[1];
        descriptions[t_idx].localRow = t_idx.local[0];
        descriptions[t_idx].localColumn= t_idx.local[1];
    });

    // Print out the Description structure for each element in the matrix.
    // Tiles are displayed in red and green to distinguish them from each other.
    SetConsoleSize(100, 150);
    for (int row = 0; row < ROWS; row++) {
        for (int column = 0; column < COLS; column++) {
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);
            std::cout << "Value: " << std::setw(2) << descriptions(row, column).value << "      ";
        }
        std::cout << "\n";

        for (int column = 0; column < COLS; column++) {
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);
            std::cout << "Tile:   " << "(" << descriptions(row, column).tileRow << "," << descriptions(row, column).tileColumn << ")  ";
        }
        std::cout << "\n";

        for (int column = 0; column < COLS; column++) {
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);
            std::cout << "Global: " << "(" << descriptions(row, column).globalRow << "," << descriptions(row, column).globalColumn << ")  ";
        }
        std::cout << "\n";

        for (int column = 0; column < COLS; column++) {
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);
            std::cout << "Local:  " << "(" << descriptions(row, column).localRow << "," << descriptions(row, column).localColumn << ")  ";
        }
        std::cout << "\n";
        std::cout << "\n";
    }
}

void main() {
    TilingDescription();
    char wait;
    std::cin >> wait;
}
```

예제의 주요 작업의 정의는 `array_view` 개체와 호출 `parallel_for_each`합니다.

1. 벡터 `Description` 구조는 8 x 9에 복사 됩니다 `array_view` 개체입니다.

2. 합니다 `parallel_for_each` 메서드를 호출을 `tiled_extent` 계산 도메인 개체입니다. `tiled_extent` 개체를 호출 하 여 만들 합니다 `extent::tile()` 메서드의 `descriptions` 변수. 에 대 한 호출의 형식 매개 변수 `extent::tile()`, `<2,3>`를 2x3 타일을 만들었는지를 지정 합니다. 따라서 8x9 행렬은 12 개의 타일, 4 개의 행과 세 개의 열으로 바둑판식으로 배열 됩니다.

3. 합니다 `parallel_for_each` 메서드를 사용 하 여 호출을 `tiled_index<2,3>` 개체 (`t_idx`) 인덱스로. 인덱스의 형식 매개 변수 (`t_idx`) 계산 도메인의 형식 매개 변수와 일치 해야 합니다 (`descriptions.extent.tile< 2, 3>()`).

4. 각 스레드를 실행 하는 경우 인덱스 `t_idx` 에 스레드는 타일에 대 한 정보를 반환 합니다 (`tiled_index::tile` 속성) 및 타일 내 스레드의 위치 (`tiled_index::local` 속성).

## <a name="tile-synchronizationtilestatic-and-tilebarrierwait"></a>타일 동기화 — tile_static 및 tile_barrier:: wait

앞의 예제는 바둑판식 레이아웃 및 인덱스를 보여 줍니다 이지만 그 자체로 매우 유용한 아닙니다.  바둑판식 타일은 알고리즘 및 악용에 통합 하는 경우 유용 `tile_static` 변수입니다. 타일의 스레드를 모두에 액세스할 수 있으므로 `tile_static` 변수, 호출 `tile_barrier::wait` 에 대 한 액세스를 동기화 하는 데 사용 되는 `tile_static` 변수입니다. 에 대 한 액세스를 갖지만 모든 타일에서 스레드를 `tile_static` 변수인 타일에서 스레드 실행의 보장 된 순서가 없습니다. 다음 예제에서는 사용 하는 방법을 보여 줍니다 `tile_static` 변수 및 `tile_barrier::wait` 각 타일의 평균 값을 계산 하는 방법입니다. 이 예제에서는 이해 하기 위해서는 다음과 같습니다.

1. RawData는 8 x 8 매트릭스에 저장 됩니다.

2. 타일 크기는 2x2입니다. 타일 포함 된 4x4 표를 만들고 사용 하 여 평균 4 x 4 매트릭스에 저장할 수 있습니다는 `array` 개체입니다. AMP 제한 함수에 대 한 참조로 캡처할 수 있는 형식의 수를 제한 되어 있습니다. `array` 클래스는 그 중 하나입니다.

3. 행렬 크기와 샘플 크기를 사용 하 여 정의 된 `#define` 문 때문에 형식 매개 변수 `array`를 `array_view`, `extent`, 및 `tiled_index` 상수 값 이어야 합니다. 사용할 수도 있습니다 `const int static` 선언 합니다. 추가 점으로 4x4 타일 평균을 계산 하려면 샘플 크기를 변경 하는 것이 간단 합니다.

4. `tile_static` 각 타일에 대해 2x2 부동 값 배열이 선언 됩니다. 선언은 모든 스레드에 대 한 코드 경로에 있는 경우에 행렬의 각 타일에 대해 하나의 배열만이 만들어집니다.

5. 각 타일의 값을 복사 하는 코드 줄이는 `tile_static` 배열입니다. 각 스레드에 대 한 값을 배열에 복사 된 후 실행 스레드에서 중지에 대 한 호출으로 인해 `tile_barrier::wait`합니다.

6. 장벽에 도달한 모든 타일에서 스레드의 경우에 평균을 계산할 수 있습니다. 모든 스레드에 대 한 코드를 실행 하므로 `if` 만 하나의 스레드에서 평균을 계산 하는 문입니다. 평균은 평균은 평균 변수에 저장 됩니다. 장벽에 사용할 수 만큼 타일로 계산을 제어 하는 구문 기본적으로입니다는 `for` 루프입니다.

7. 데이터를 `averages` 이기 때문에 변수를 `array` 개체를 다시 호스트에 복사 해야 합니다. 이 예제에서는 벡터 변환 연산자를 사용 합니다.

8. 전체 예제에서 SAMPLESIZE를 4로 변경할 수 있습니다 하 고 다른 변경 하지 않고 코드를 제대로 실행 합니다.

```cpp
#include <iostream>
#include <amp.h>
using namespace concurrency;

#define SAMPLESIZE 2
#define MATRIXSIZE 8
void SamplingExample() {

    // Create data and array_view for the matrix.
    std::vector<float> rawData;
    for (int i = 0; i < MATRIXSIZE * MATRIXSIZE; i++) {
        rawData.push_back((float)i);
    }
    extent<2> dataExtent(MATRIXSIZE, MATRIXSIZE);
    array_view<float, 2> matrix(dataExtent, rawData);

    // Create the array for the averages.
    // There is one element in the output for each tile in the data.
    std::vector<float> outputData;
    int outputSize = MATRIXSIZE / SAMPLESIZE;
    for (int j = 0; j < outputSize * outputSize; j++) {
        outputData.push_back((float)0);
    }
    extent<2> outputExtent(MATRIXSIZE / SAMPLESIZE, MATRIXSIZE / SAMPLESIZE);
    array<float, 2> averages(outputExtent, outputData.begin(), outputData.end());

    // Use tiles that are SAMPLESIZE x SAMPLESIZE.
    // Find the average of the values in each tile.
    // The only reference-type variable you can pass into the parallel_for_each call
    // is a concurrency::array.
    parallel_for_each(matrix.extent.tile<SAMPLESIZE, SAMPLESIZE>(),
        [=, &averages] (tiled_index<SAMPLESIZE, SAMPLESIZE> t_idx) restrict(amp)
    {
        // Copy the values of the tile into a tile-sized array.
        tile_static float tileValues[SAMPLESIZE][SAMPLESIZE];
        tileValues[t_idx.local[0]][t_idx.local[1]] = matrix[t_idx];

        // Wait for the tile-sized array to load before you calculate the average.
        t_idx.barrier.wait();

        // If you remove the if statement, then the calculation executes for every
        // thread in the tile, and makes the same assignment to averages each time.
        if (t_idx.local[0] == 0 && t_idx.local[1] == 0) {
            for (int trow = 0; trow < SAMPLESIZE; trow++) {
                for (int tcol = 0; tcol < SAMPLESIZE; tcol++) {
                    averages(t_idx.tile[0],t_idx.tile[1]) += tileValues[trow][tcol];
                }
            }
            averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE * SAMPLESIZE);
        }
    });

    // Print out the results.
    // You cannot access the values in averages directly. You must copy them
    // back to a CPU variable.
    outputData = averages;
    for (int row = 0; row < outputSize; row++) {
        for (int col = 0; col < outputSize; col++) {
            std::cout << outputData[row*outputSize + col] << " ";
        }
        std::cout << "\n";
    }
    // Output for SAMPLESSIZE = 2 is:
    //  4.5  6.5  8.5 10.5
    // 20.5 22.5 24.5 26.5
    // 36.5 38.5 40.5 42.5
    // 52.5 54.5 56.5 58.5

    // Output for SAMPLESIZE = 4 is:
    // 13.5 17.5
    // 45.5 49.5
}

int main() {
    SamplingExample();
}
```

## <a name="race-conditions"></a>경합 조건

만들려는 만들고자 할를 `tile_static` 라는 변수 `total` 다음과 같은 각 스레드에 대해 해당 변수를 증가 및:

```cpp
// Do not do this.
tile_static float total;
total += matrix[t_idx];
t_idx.barrier.wait();

averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE* SAMPLESIZE);
```

이 방법 사용 하 여 첫 번째 문제는 `tile_static` 변수 이니셜라이저를 포함할 수 없습니다. 두 번째 문제에 대 한 할당에 경합 상태가 있는지는 `total`이므로 특정 순서 없이 변수에 액세스할 수 있는 모든 타일에서 스레드입니다. 다음과 같이 하나의 스레드를 각 장벽의 합계에, 액세스를 허용 하는 알고리즘을 프로그래밍할 수 있습니다. 그러나이 솔루션은 확장할 수 없습니다.

```cpp
// Do not do this.
tile_static float total;
if (t_idx.local[0] == 0&& t_idx.local[1] == 0) {
    total = matrix[t_idx];
}
t_idx.barrier.wait();

if (t_idx.local[0] == 0&& t_idx.local[1] == 1) {
    total += matrix[t_idx];
}
t_idx.barrier.wait();

// etc.
```

## <a name="memory-fences"></a>메모리 펜스

두 가지 종류의 동기화 해야 하는 메모리 액세스-전역 메모리 액세스 및 `tile_static` 메모리 액세스 합니다. `concurrency::array` 개체는 전역 메모리만 할당 합니다. A `concurrency::array_view` 전역 메모리를 참조할 수 있습니다 `tile_static` 메모리 또는 생성 된 방식에 따라 둘 다.  동기화 해야 하는 메모리의 두 종류가 있습니다.

- 전역 메모리

- `tile_static`

A *메모리 펜스* 메모리 액세스가 스레드 타일의 다른 스레드를 사용할 수 있고 메모리 액세스가 프로그램 순서에 따라 실행 되도록 합니다. 이 위해 컴파일러와 프로세서가 수행 순서를 변경 하지 읽기 및 쓰기는 펜스에서. C++ AMP 메모리 펜스를 이러한 방법 중 하나를 호출 하 여 만들어집니다.

- [tile_barrier:: wait 메서드](reference/tile-barrier-class.md#wait): 전역 주변에 펜스를 만듭니다 및 `tile_static` 메모리입니다.

- [tile_barrier:: wait_with_all_memory_fence 메서드](reference/tile-barrier-class.md#wait_with_all_memory_fence): 전역 주변에 펜스를 만듭니다 및 `tile_static` 메모리입니다.

- [tile_barrier:: wait_with_global_memory_fence 메서드](reference/tile-barrier-class.md#wait_with_global_memory_fence): 주변에 전역 메모리 펜스를 만듭니다.

- [tile_barrier:: wait_with_tile_static_memory_fence 메서드](reference/tile-barrier-class.md#wait_with_tile_static_memory_fence): 주변에 펜스를 만듭니다 `tile_static` 메모리입니다.

앱의 성능을 향상 시킬 수 있습니다 필요한 특정 펜스를 호출 합니다. Barrier 형식은 컴파일러와 하드웨어 문을 다시 정렬 하는 방법을 하는 영향을 줍니다. 예를 들어 전역 메모리 펜스를 사용 하 여만 전역 메모리 액세스에 적용 되는 컴파일러와 하드웨어 다시 정렬할 수 있습니다 따라서 경우 읽고 쓸 `tile_static` 는 펜스의 양면에 있는 변수입니다.

다음 예제에서는 장벽에 쓰기를 동기화 `tileValues`, `tile_static` 변수입니다. 이 예에서 `tile_barrier::wait_with_tile_static_memory_fence` 대신 라고 `tile_barrier::wait`합니다.

```cpp
// Using a tile_static memory fence.
parallel_for_each(matrix.extent.tile<SAMPLESIZE, SAMPLESIZE>(),
    [=, &averages] (tiled_index<SAMPLESIZE, SAMPLESIZE> t_idx) restrict(amp)
{
    // Copy the values of the tile into a tile-sized array.
    tile_static float tileValues[SAMPLESIZE][SAMPLESIZE];
    tileValues[t_idx.local[0]][t_idx.local[1]] = matrix[t_idx];

    // Wait for the tile-sized array to load before calculating the average.
    t_idx.barrier.wait_with_tile_static_memory_fence();

    // If you remove the if statement, then the calculation executes
    // for every thread in the tile, and makes the same assignment to
    // averages each time.
    if (t_idx.local[0] == 0&& t_idx.local[1] == 0) {
        for (int trow = 0; trow <SAMPLESIZE; trow++) {
            for (int tcol = 0; tcol <SAMPLESIZE; tcol++) {
                averages(t_idx.tile[0],t_idx.tile[1]) += tileValues[trow][tcol];
            }
        }
    averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE* SAMPLESIZE);
    }
});
```

## <a name="see-also"></a>참고자료

[C++ AMP(C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[tile_static 키워드](../../cpp/tile-static-keyword.md)
