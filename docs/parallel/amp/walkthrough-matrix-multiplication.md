---
title: '연습: 행렬 곱'
ms.date: 04/23/2019
ms.assetid: 61172e8b-da71-4200-a462-ff3a908ab0cf
ms.openlocfilehash: afa9dba8938f9d701b8f21ca3575eb06eb688ac0
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877478"
---
# <a name="walkthrough-matrix-multiplication"></a>연습: 행렬 곱

이 단계별 연습에 사용 하는 방법을 보여 줍니다. C++ AMP가 행렬 곱셈의 실행을 가속화 합니다. 바둑판식 배열을 사용 하 여 여러 개 있는 바둑판식 배열 없이 한 두 가지 알고리즘 표시 됩니다.

## <a name="prerequisites"></a>전제 조건

시작하기 전에

- 읽기 [ C++ AMP 개요](../../parallel/amp/cpp-amp-overview.md)합니다.

- 읽기 [타일을 사용 하 여](../../parallel/amp/using-tiles.md)입니다.

- 이상 실행 해야 Windows 7 또는 Windows Server 2008 R2.

### <a name="to-create-the-project"></a>프로젝트를 만들려면

새 프로젝트를 만들기 위한 지침은 Visual Studio 버전을 설치한 경우에 따라 달라 집니다. 버전 선택기를 올바른 버전으로 설정 왼쪽 위에 있는 있는지 확인 합니다.

::: moniker range="vs-2019"

### <a name="to-create-the-project-in-visual-studio-2019"></a>Visual Studio 2019에 프로젝트를 만들려면

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트** 열려는 합니다 **새 프로젝트를 만들** 대화 상자.

1. 설정 대화 상자 맨 **언어** 를 **C++** 설정 **플랫폼** 하 **Windows**, 설정 및 **프로젝트 형식을** 하 **콘솔**합니다. 

1. 필터링된 된 프로젝트 형식 목록에서 선택 **빈 프로젝트** 선택한 **다음**합니다. 다음 페이지에서 입력 *MatrixMultiply* 에 **이름** 상자에 프로젝트의 이름을 지정 하 고 원하는 경우 프로젝트 위치를 지정 합니다.

   ![새 콘솔 앱](../../build/media/mathclient-project-name-2019.png "새 콘솔 앱")

1. 선택 된 **만들기** 클라이언트 프로젝트를 만들려면 단추입니다.

1. **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고 **소스 파일**를 선택한 후 **추가** > **새 항목**합니다.

1. 에 **새 항목 추가** 대화 상자에서  **C++ 파일 (.cpp)** 를 입력 *MatrixMultiply.cpp* 에 **이름** 상자를 선택한 후를 **추가** 단추입니다.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-project-in-visual-studio-2017-or-2015"></a>Visual Studio 2017 또는 2015에서 프로젝트를 만들려면

1. Visual Studio의 메뉴 모음에서 선택 **파일** > **새로 만들기** > **프로젝트**합니다.

1. 아래 **설치 됨** 템플릿 창에서 선택 **시각적 C++** 합니다.

1. 선택 **빈 프로젝트**를 입력 *MatrixMultiply* 에 **이름** 상자를 선택한 후는 **확인** 단추입니다.

1. **다음** 단추를 선택합니다.

1. **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고 **소스 파일**를 선택한 후 **추가** > **새 항목**합니다.

1. 에 **새 항목 추가** 대화 상자에서  **C++ 파일 (.cpp)** 를 입력 *MatrixMultiply.cpp* 에 **이름** 상자를 선택한 후를 **추가** 단추입니다.

::: moniker-end

## <a name="multiplication-without-tiling"></a>바둑판식 배열 없이 곱하기

이 섹션에서는 다음과 같이 정의 된 A와 B 라는 두 행렬 곱셈을 고려 합니다.

![3&#45;에서&#45;는 행렬](../../parallel/amp/media/campmatrixanontiled.png "3&#45;에서&#45;는 행렬")

![2&#45;에서&#45;3 행렬 B](../../parallel/amp/media/campmatrixbnontiled.png "2&#45;에서&#45;3 행렬 B")

3을 2 행렬 이며 B가 2 ~ 3 행렬입니다. B가 곱하는 a 제품은 다음-3x3 매트릭스입니다. 제품 b 요소 별로 열을 기준으로 행을 곱하여 계산 됩니다.

![3&#45;에서&#45;3 제품 매트릭스](../../parallel/amp/media/campmatrixproductnontiled.png "3&#45;에서&#45;의 3 개 제품 매트릭스")

### <a name="to-multiply-without-using-c-amp"></a>사용 하지 않고 곱할 C++ AMP

1. MatrixMultiply.cpp 열고 기존 코드를 대체 하려면 다음 코드를 사용 합니다.

   ```cpp
   #include <iostream>

   void MultiplyWithOutAMP() {
       int aMatrix[3][2] = {{1, 4}, {2, 5}, {3, 6}};
       int bMatrix[2][3] = {{7, 8, 9}, {10, 11, 12}};
       int product[3][3] = {{0, 0, 0}, {0, 0, 0}, {0, 0, 0}};

       for (int row = 0; row < 3; row++) {
           for (int col = 0; col < 3; col++) {
               // Multiply the row of A by the column of B to get the row, column of product.
               for (int inner = 0; inner < 2; inner++) {
                   product[row][col] += aMatrix[row][inner] * bMatrix[inner][col];
               }
               std::cout << product[row][col] << "  ";
           }
           std::cout << "\n";
       }
   }

   void main() {
       MultiplyWithOutAMP();
       getchar();
   }
   ```

   알고리즘 정의 행렬 곱셈의 간단한 구현입니다. 계산 시간을 줄이기 위해 모든 스레드 또는 병렬 알고리즘을 사용 하지 않습니다.

1. 메뉴 모음에서 **파일** > **모두 저장**을 차례로 선택합니다.

1. 선택 된 **F5** 바로 가기 키를 디버깅을 시작 하 고 출력 올바른지 확인 합니다.

1. 선택할 **Enter** 응용 프로그램을 종료 합니다.

### <a name="to-multiply-by-using-c-amp"></a>사용 하 여 곱할 C++ AMP

1. MatrixMultiply.cpp를 추가 하기 전에 다음 코드는 `main` 메서드.

   ```cpp
   void MultiplyWithAMP() {
   int aMatrix[] = { 1, 4, 2, 5, 3, 6 };
   int bMatrix[] = { 7, 8, 9, 10, 11, 12 };
   int productMatrix[] = { 0, 0, 0, 0, 0, 0, 0, 0, 0 };

   array_view<int, 2> a(3, 2, aMatrix);

   array_view<int, 2> b(2, 3, bMatrix);

   array_view<int, 2> product(3, 3, productMatrix);

   parallel_for_each(product.extent,
      [=] (index<2> idx) restrict(amp) {
          int row = idx[0];
          int col = idx[1];
          for (int inner = 0; inner <2; inner++) {
              product[idx] += a(row, inner)* b(inner, col);
          }
      });

   product.synchronize();

   for (int row = 0; row <3; row++) {
      for (int col = 0; col <3; col++) {
          //std::cout << productMatrix[row*3 + col] << "  ";
          std::cout << product(row, col) << "  ";
      }
      std::cout << "\n";
     }
   }
   ```

   AMP 코드에는 비 AMP 코드와 유사 합니다. 에 대 한 호출 `parallel_for_each` 의 각 요소에 대해 하나의 스레드를 시작 `product.extent`, 대체 및는 `for` 행 및 열에 대 한 루프입니다. 행과 열에 있는 셀의 값은 영어로 `idx`합니다. 요소에 액세스할 수 있습니다는 `array_view` 중 하나를 사용 하 여 개체를 `[]` 연산자 및 변수를 인덱스 또는 `()` 연산자와 행 및 열 변수. 이 예제에서는 두 방법을 보여 줍니다. 합니다 `array_view::synchronize` 의 값을 복사 하는 메서드를 `product` 변수를 다시는 `productMatrix` 변수입니다.

1. 다음을 추가 합니다 `include` 고 `using` MatrixMultiply.cpp 맨 위에 있는 문.

   ```cpp
   #include <amp.h>
   using namespace concurrency;
   ```

1. 수정 된 `main` 메서드를 호출 하는 `MultiplyWithAMP` 메서드.

   ```cpp
   void main() {
       MultiplyWithOutAMP();
       MultiplyWithAMP();
       getchar();
   }
   ```

1. 키를 눌러 합니다 **Ctrl**+**F5** 바로 가기 키를 디버깅을 시작 하 고 출력 올바른지 확인 합니다.

1. 키를 눌러 합니다 **스페이스바** 응용 프로그램을 종료 합니다.

## <a name="multiplication-with-tiling"></a>바둑판식 배열 사용 하 여 곱하기

바둑판식 배열에는 데이터를 같은 크기의 하위 집합 타일 이라고를 분할 하는 기술입니다. 다음 세 가지 바둑판식 배열을 사용 하는 경우 변경 합니다.

- 만들 수 있습니다 `tile_static` 변수입니다. 데이터에 액세스를 `tile_static` 공간 전역 공간에서 데이터에 대 한 액세스 보다 몇 배나 빠르다는 수 있습니다. 인스턴스의 `tile_static` 변수 각 타일에 대해 생성 되 고 타일에 있는 모든 스레드가 변수에 액세스할 수 있습니다. 바둑판식 배열의 가장 큰 이점은 성능 향상으로 인해 `tile_static` 액세스 합니다.

- 호출할 수 있습니다 합니다 [tile_barrier:: wait](reference/tile-barrier-class.md#wait) 모든 지정 된 코드 줄에 하나의 타일에서 스레드를 중지 하는 방법입니다. 스레드가에서는 실행 되는 순서를 보장할 수 없는 호출 될 때 중지 됩니다 모든 스레드가 하나의 타일로 `tile_barrier::wait` 실행을 계속 하기 전에 합니다.

- 전체 상대적인 스레드 인덱스에 액세스할 수 있는 `array_view` 개체 및 타일에 상대적인 인덱스입니다. 로컬 인덱스를 사용 보다 쉽게 읽고 디버깅할 코드를 만들 수 있습니다.

를 이용 하려면 바둑판식 배열에서 행렬 곱 알고리즘 행렬을 타일로 분할 하며 타일 데이터를 복사 `tile_static` 빠른 액세스에 대 한 변수입니다. 이 예제에서는 행렬은 동일한 크기의 submatrices에 분할 됩니다. 제품을는 submatrices 곱하여 찾을 수 있습니다. 두 매트릭스 및이 예제의 제품 같습니다.

![4&#45;에서&#45;는 4 매트릭스](../../parallel/amp/media/campmatrixatiled.png "4&#45;에서&#45;4 매트릭스는")

![4&#45;에서&#45;4 매트릭스 B](../../parallel/amp/media/campmatrixbtiled.png "4&#45;에서&#45;4 매트릭스 B")

![4&#45;에서&#45;4 제품 행렬](../../parallel/amp/media/campmatrixproducttiled.png "4&#45;에서&#45;의 4 제품 매트릭스")

매트릭스가 다음과 같이 정의 된 4 개의 2x2 행렬으로 분할 됩니다.

![4&#45;에서&#45;4 매트릭스는 2로 분할 된&#45;에서&#45;2 하위&#45;행렬](../../parallel/amp/media/campmatrixapartitioned.png "4&#45;에서&#45;4 매트릭스는 2로 분할 된&#45;에서&#45;2 하위&#45;행렬")

![4&#45;에서&#45;4 매트릭스 B가 2를 분할할&#45;에서&#45;2 하위&#45;행렬](../../parallel/amp/media/campmatrixbpartitioned.png "4&#45;에서&#45;4 매트릭스 B가 2를 분할할&#45;에서&#45;2 하위&#45;행렬")

A 제품 B 현재의 기록 고 다음과 같이 계산할 수 있습니다.

![4&#45;에서&#45;4 매트릭스는 B 2로 분할 된&#45;에서&#45;2 하위&#45;행렬](../../parallel/amp/media/campmatrixproductpartitioned.png "4&#45;에서&#45;4 매트릭스는 B 2로 분할 된&#45;에서&#45;2 하위&#45;행렬")

때문에 행렬 `a` 를 통해 `h` 2x2 행렬의 모든 제품 이며의 합계도 2x2 행렬입니다. 따르는 것 제품 a 고 B는 4x4 행렬을 예상 합니다. 알고리즘을 신속 하 게 확인 하려면 첫 번째 행의 요소, 제품의 첫 번째 열 값을 계산 합니다. 예제에서는 되는 요소의 값은 첫 번째 행과 첫째 열에 `ae + bg`입니다. 첫 번째 행을 첫 번째 열을 계산 해야 `ae` 고 `bg` 각 용어에 대 한 합니다. 해당 값에 대 한 `ae` 는 `(1 * 1) + (2 * 5) = 11`합니다. 에 대 한 값 `bg` 는 `(3 * 1) + (4 * 5) = 23`합니다. 최종 값은 `11 + 23 = 34`, 올바른 인 합니다.

이 알고리즘을 코드를 구현 합니다.

- 사용 하는 `tiled_extent` 개체 대신는 `extent` 개체는 `parallel_for_each` 호출 합니다.

- 사용 하는 `tiled_index` 개체 대신는 `index` 개체는 `parallel_for_each` 호출 합니다.

- 만듭니다 `tile_static` submatrices를 보유할 변수입니다.

- 사용 된 `tile_barrier::wait` 는 submatrices의 제품에 대 한 계산에 대 한 스레드를 중지 하는 방법입니다.

### <a name="to-multiply-by-using-amp-and-tiling"></a>바둑판식 배열 및 AMP를 사용 하 여 곱할

1. MatrixMultiply.cpp를 추가 하기 전에 다음 코드는 `main` 메서드.

   ```cpp
   void MultiplyWithTiling() {
       // The tile size is 2.
       static const int TS = 2;

       // The raw data.
       int aMatrix[] = { 1, 2, 3, 4, 5, 6, 7, 8, 1, 2, 3, 4, 5, 6, 7, 8 };
       int bMatrix[] = { 1, 2, 3, 4, 5, 6, 7, 8, 1, 2, 3, 4, 5, 6, 7, 8 };
       int productMatrix[] = { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 };

       // Create the array_view objects.
       array_view<int, 2> a(4, 4, aMatrix);
       array_view<int, 2> b(4, 4, bMatrix);
       array_view<int, 2> product(4, 4, productMatrix);

       // Call parallel_for_each by using 2x2 tiles.
       parallel_for_each(product.extent.tile<TS, TS>(),
           [=] (tiled_index<TS, TS> t_idx) restrict(amp)
           {
               // Get the location of the thread relative to the tile (row, col)
               // and the entire array_view (rowGlobal, colGlobal).
               int row = t_idx.local[0];
               int col = t_idx.local[1];
               int rowGlobal = t_idx.global[0];
               int colGlobal = t_idx.global[1];
               int sum = 0;

               // Given a 4x4 matrix and a 2x2 tile size, this loop executes twice for each thread.
               // For the first tile and the first loop, it copies a into locA and e into locB.
               // For the first tile and the second loop, it copies b into locA and g into locB.
               for (int i = 0; i < 4; i += TS) {
                   tile_static int locA[TS][TS];
                   tile_static int locB[TS][TS];
                   locA[row][col] = a(rowGlobal, col + i);
                   locB[row][col] = b(row + i, colGlobal);
                   // The threads in the tile all wait here until locA and locB are filled.
                   t_idx.barrier.wait();

                   // Return the product for the thread. The sum is retained across
                   // both iterations of the loop, in effect adding the two products
                   // together, for example, a*e.
                   for (int k = 0; k < TS; k++) {
                       sum += locA[row][k] * locB[k][col];
                   }

                   // All threads must wait until the sums are calculated. If any threads
                   // moved ahead, the values in locA and locB would change.
                   t_idx.barrier.wait();
                   // Now go on to the next iteration of the loop.
               }

               // After both iterations of the loop, copy the sum to the product variable by using the global location.
               product[t_idx.global] = sum;
           });

       // Copy the contents of product back to the productMatrix variable.
       product.synchronize();

       for (int row = 0; row <4; row++) {
           for (int col = 0; col <4; col++) {
               // The results are available from both the product and productMatrix variables.
               //std::cout << productMatrix[row*3 + col] << "  ";
               std::cout << product(row, col) << "  ";
           }
           std::cout << "\n";
       }
   }
   ```

   이 예제는 바둑판식 배열 없이 크게 다릅니다. 코드는 이러한 개념적 단계를 사용합니다.
   1. [0, 0] 타일의 요소를 복사 `a` 에 `locA`입니다. [0, 0] 타일의 요소를 복사 `b` 에 `locB`입니다. 있음을 `product` 는 바둑판식으로 표시 되지 않습니다 `a` 고 `b`입니다. 따라서 액세스 하려면 전역 인덱스를 사용할 `a, b`, 및 `product`합니다. 에 대 한 호출 `tile_barrier::wait` 반드시 필요 합니다. 모든 타일에서 스레드가 될 때까지 중지 `locA` 및 `locB` 채워집니다.

   1. 곱하기 `locA` 하 고 `locB` 결과에 넣은 `product`합니다.

   1. [0, 1]의 타일의 요소를 복사 `a` 에 `locA`입니다. [1, 0] 타일의 요소를 복사 `b` 에 `locB`입니다.

   1. 곱하기 `locA` 하 고 `locB` 에 이미 있는 결과에 추가할 `product`합니다.

   1. [0, 0] 타일에 대 한 곱하기 완료 되었습니다.

   1. 다른 4 개의 타일에 대해 반복 합니다. 타일에 맞게 없음 인덱싱 되며 스레드 순서에 관계 없이 실행할 수 있습니다. 각 스레드가 실행 되는 `tile_static` 변수는 적절 하 게 각 타일에 대해 생성 됩니다 및 호출 `tile_barrier::wait` 프로그램 흐름을 제어 합니다.

   1. 알고리즘을 자세히 살펴보면 각 submatrix 로드 확인을 `tile_static` 메모리를 두 번입니다. 해당 데이터를 전송 하는 데 시간이 걸릴지 않습니다. 그러나 데이터 되 면 `tile_static` 메모리, 데이터 액세스를 훨씬 더 빠릅니다. 제품을 계산 합니다 submatrices 값으로 반복 되는 액세스를 필요로 하므로 전체 성능 향상을 있습니다. 각 알고리즘을 실험 최적의 알고리즘을 찾고 타일 크기에 필요 합니다.

   비 AMP 및 비 타일 예제에서는 A의 각 요소 곱을 계산 하는 전역 메모리에서 B 4 배를 액세스 하는 고 합니다. 바둑판식 배열 예제에서는 각 요소에 액세스할 때 두 번 전역 메모리에서 4 배를 `tile_static` 메모리입니다. 상당한 수준의 성능 향상은 아닙니다. 그러나 A와 B에 1024x1024 되었으면 행렬 및 타일 크기 된 16, 성능이 크게 향상 됩니다. 이 경우 각 요소는 복사할 `tile_static` 메모리만 16 시간 및에서 액세스할 `tile_static` 1024 시간은 메모리입니다.

1. 기본 메서드를 호출 하도록 수정 된 `MultiplyWithTiling` 메서드를 표시 합니다.

   ```cpp
   void main() {
       MultiplyWithOutAMP();
       MultiplyWithAMP();
       MultiplyWithTiling();
       getchar();
   }
   ```

1. 키를 눌러 합니다 **Ctrl**+**F5** 바로 가기 키를 디버깅을 시작 하 고 출력 올바른지 확인 합니다.

1. 키를 눌러 합니다 **공간** 모음 응용 프로그램을 종료 합니다.

## <a name="see-also"></a>참고자료

[C++ AMP(C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[연습: C++ AMP 애플리케이션 디버깅](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)
