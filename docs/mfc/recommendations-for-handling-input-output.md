---
title: 입력-출력 처리에 대 한 권장 사항
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [MFC], about I/O
- file-based I/O options
- I/O [MFC]
- I/O [MFC], options
- I/O [MFC], file-based options
ms.assetid: d664b175-3b4a-40c3-b14b-39de6b12e419
ms.openlocfilehash: 760c213c3af7f9c75374f04e3dfc6b9499eade5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218566"
---
# <a name="recommendations-for-handling-inputoutput"></a>입력/출력 처리에 대한 권장 사항

파일 기반 I/O 사용 하는지 여부는 다음과 같은 의사 결정 트리를 질문에 응답 하는 방법에 따라 달라 집니다.

**디스크 파일에 응용 프로그램의 기본 데이터가 상주지 않습니다**

- 예, 기본 데이터는 디스크 파일에 상주합니다.

     **응용 프로그램 전체 파일을 메모리로 파일 열기에 읽기 및 쓰기 전체 파일을 다시 디스크에 파일 저장**

   - 예: 이 경우 기본 MFC 문서. 사용 하 여 `CDocument` 직렬화 합니다.

   - 아니요: 이 경우 일반적으로 파일의 업데이트 트랜잭션 기반 합니다. 트랜잭션당 기준 파일을 업데이트 하 고 필요 하지 않습니다 `CDocument` 직렬화 합니다.

- 아니요, 기본 데이터 디스크 파일에 상주 하지 않습니다.

     **ODBC 데이터 소스에서 데이터 상주는**

   - 예, 데이터를 ODBC 데이터 원본에 있습니다.

         Use MFC's database support. The standard MFC implementation for this case includes a `CDatabase` object, as discussed in the article [MFC: Using Database Classes with Documents and Views](../data/mfc-using-database-classes-with-documents-and-views.md). The application might also read and write an auxiliary file — the purpose of the application wizard "both a database view and file support" option. In this case, you'd use serialization for the auxiliary file.

   - 아니요, ODBC 데이터 소스에서 데이터 상주 하지 않습니다.

         Examples of this case: the data resides in a non-ODBC DBMS; the data is read via some other mechanism, such as OLE or DDE.

         In such cases, you won't use serialization, and your application won't have Open and Save menu items. You might still want to use a `CDocument` as a home base, just as an MFC ODBC application uses the document to store `CRecordset` objects. But you won't use the framework's default File Open/Save document serialization.

열기, 저장, 지원과 파일 메뉴에서 명령으로 저장, 프레임 워크 문서 직렬화를 제공 합니다. Serialization 읽고 클래스에서 파생 된 개체를 포함 하 여 데이터를 쓸 `CObject`에 영구 저장소, 일반적으로 디스크 파일입니다. Serialization 사용 하기 쉬운 되어 다양 한 요구 사항을 제공 되지만 많은 데이터 액세스 응용 프로그램에서 적절 한 수입니다. 데이터 액세스 응용 프로그램은 일반적으로 트랜잭션당 기준 데이터를 업데이트 합니다. 트랜잭션 보다는 읽기 및 쓰기 전체 데이터 파일을 한 번에 영향을 받는 레코드를 업데이트 합니다.

Serialization에 대 한 자세한 내용은 [Serialization](../mfc/serialization-in-mfc.md)합니다.

## <a name="see-also"></a>참고자료

[Serialization: Serialization 및 입/출력 데이터베이스](../mfc/serialization-serialization-vs-database-input-output.md)
