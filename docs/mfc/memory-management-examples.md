---
title: "メモリ管理 : 例 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "配列 [C++], 割り当て (リソースの)"
  - "配列 [C++], メモリ管理"
  - "データ構造 [C++]"
  - "データ構造 [C++], 割り当て (メモリの)"
  - "例 [MFC], メモリの割り当て"
  - "フレーム割り当て"
  - "ヒープ割り当て, 例"
  - "メモリの割り当て [C++], 配列"
  - "メモリの割り当て [C++], データ構造"
  - "メモリの割り当て [C++], 例"
  - "メモリの割り当て [C++], オブジェクト"
  - "MFC [C++], メモリ管理"
  - "オブジェクト [C++], 割り当て (メモリの)"
  - "オブジェクト [C++], メモリの割り当て"
  - "構造体のメモリ割り当て"
  - "型 [C++], メモリの割り当て"
ms.assetid: f10240f8-b698-4c83-9288-97a54318930b
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# メモリ管理 : 例
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、MFC によるメモリ割り当ての 3 種類の一般的な種類のフレームの割り当てとヒープ割り当てをどのように実行するかについて説明します。:  
  
-   [バイトの配列](#_core_allocation_of_an_array_of_bytes)  
  
-   [データ構造](#_core_allocation_of_a_data_structure)  
  
-   [オブジェクト。](#_core_allocation_of_an_object)  
  
##  <a name="_core_allocation_of_an_array_of_bytes"></a> バイトの配列の割り当て  
  
#### フレームのバイト配列を割り当てます。  
  
1.  次のコードに示すように、配列を定義します。  配列は自動的に削除され、メモリが配列変数がスコープを終了したときにクリアされます。  
  
     [!code-cpp[NVC_MFC_Utilities#1](../mfc/codesnippet/CPP/memory-management-examples_1.cpp)]  
  
#### ヒープのバイト \(またはプリミティブ データ型\) の配列を割り当てます。  
  
1.  この例では、配列の構文の **new** の演算子の使用:  
  
     [!code-cpp[NVC_MFC_Utilities#2](../mfc/codesnippet/CPP/memory-management-examples_2.cpp)]  
  
#### ヒープから配列を解放するには  
  
1.  次のよう **delete** の演算子の使用:  
  
     [!code-cpp[NVC_MFC_Utilities#3](../mfc/codesnippet/CPP/memory-management-examples_3.cpp)]  
  
##  <a name="_core_allocation_of_a_data_structure"></a> データ構造の割り当て  
  
#### フレームのデータ構造を割り当てます。  
  
1.  次のように構造体変数を定義する:  
  
     [!code-cpp[NVC_MFC_Utilities#4](../mfc/codesnippet/CPP/memory-management-examples_4.cpp)]  
  
     構造体が占有するメモリはスコープを終了したときにクリアされます。  
  
#### ヒープ データの構造を割り当てます。  
  
1.  ヒープと **delete** のデータ構造を次の例に示すように、解放するために割り当てるために **new** を使用する:  
  
     [!code-cpp[NVC_MFC_Utilities#5](../mfc/codesnippet/CPP/memory-management-examples_5.cpp)]  
  
##  <a name="_core_allocation_of_an_object"></a> オブジェクトの割り当て  
  
#### フレーム オブジェクトを割り当てます。  
  
1.  次のようなオブジェクトを宣言する:  
  
     [!code-cpp[NVC_MFC_Utilities#6](../mfc/codesnippet/CPP/memory-management-examples_6.cpp)]  
  
     オブジェクトのデストラクターが自動的にオブジェクトがスコープを終了するときに呼び出されます。  
  
#### ヒープのオブジェクトを割り当てます。  
  
1.  オブジェクトへのポインターを返すヒープ オブジェクトを代入するに **new** の演算子を使用します。  コントロールを削除するには **delete** の演算子を使用します。  
  
     次のヒープとフレームの例は `CPerson` のコンストラクターは、引数を受け取らないことを前提としています。  
  
     [!code-cpp[NVC_MFC_Utilities#7](../mfc/codesnippet/CPP/memory-management-examples_7.cpp)]  
  
     `CPerson` のコンストラクターの引数が `char`へのポインターである場合、フレームの割り当てのステートメントは、次の操作:  
  
     [!code-cpp[NVC_MFC_Utilities#8](../mfc/codesnippet/CPP/memory-management-examples_8.cpp)]  
  
     ヒープ割り当てのステートメントは、次の操作:  
  
     [!code-cpp[NVC_MFC_Utilities#9](../mfc/codesnippet/CPP/memory-management-examples_9.cpp)]  
  
## 参照  
 [メモリ管理 : ヒープ割り当て](../mfc/memory-management-heap-allocation.md)