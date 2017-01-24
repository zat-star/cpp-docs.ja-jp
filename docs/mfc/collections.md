---
title: "コレクション クラス | Microsoft Docs"
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
  - "配列のテンプレート"
  - "配列 [C++], クラス"
  - "コレクション クラス, コレクション クラスの概要"
  - "コレクション クラス, 配列"
  - "コレクション クラス, 一覧"
  - "コレクション クラス, マップ"
  - "コレクション クラス, MFC"
  - "コレクション クラス, 形状"
  - "コレクション クラス, テンプレート ベースの"
  - "コレクション, 概要 (コレクションの)"
  - "MFC コレクション クラス"
  - "MFC, コレクション"
  - "形状"
  - "形状, コレクション"
ms.assetid: 02586e4c-851d-41d0-a722-feb11c17c74c
caps.latest.revision: 18
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# コレクション クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC のコレクション クラスでは、オブジェクトのグループを管理できます。  次の 2 種類のコレクション クラスがあります。  
  
-   [C\+\+ テンプレートから作成したコレクション クラス](#_core_the_template.2d.based_collection_classes)  
  
-   [テンプレートで作成されていないコレクション クラス](#_core_the_collection_classes_not_based_on_templates)  
  
> [!NOTE]
>  非テンプレート コレクション クラスを既に使用しているコードでは、引き続きそのクラスを使用できます。  独自のデータ型のためにタイプ セーフな \(型が保証された\) コレクション クラスを新規作成する場合は、テンプレート ベースのクラスの使用をお勧めします。  
  
##  <a name="_core_collection_shapes"></a> コレクション クラスの形状  
 コレクション クラスは、その "形状" と要素の型で識別されます。  この "形状" とは、コレクションにオブジェクト編成し、保存する形態のことです。  MFC では、コレクション クラスの基本形状として、リスト、配列、マップの 3 つがあります \(マップはディクショナリとも呼ばれます\)。  自分のプログラムの内容に最も合ったコレクション形状を選択できます。  
  
 コレクション クラスの 3 種類の形状のそれぞれについては、このトピックで簡単に後述します。  機能を比較してプログラムに最も適した形状を決定するには、「[コレクション クラスの選択に関する推奨事項](../Topic/Recommendations%20for%20Choosing%20a%20Collection%20Class.md)」を参照してください。  
  
-   リスト  
  
     リスト クラスは、要素を順番に並べたインデックスのないリストであり、双方向のリンク リストとして実装されます。  リストには "先頭" と "末尾" があり、リストの先頭または末尾の要素の追加や削除、または中間の要素の挿入と削除を高速で行うことができます。  
  
-   Array  
  
     配列クラスは、オブジェクトを順番に並べた、整数インデックス付きの配列です。サイズを動的に変更できます。  
  
-   マップ \(ディクショナリとも呼ばれます\)  
  
     マップは、キー オブジェクトと値オブジェクトを対応付けるコレクションです。  
  
##  <a name="_core_the_template.2d.based_collection_classes"></a> テンプレート ベースのコレクション クラス  
 任意の型のオブジェクトを含むタイプ セーフなコレクションを実装する最も簡単な方法は、MFC のテンプレート ベースのクラスを使用することです。  これらのクラスの例については、MFC サンプル [収集する](../top/visual-cpp-samples.md)を参照してください。  
  
 次の表は、MFC のテンプレート ベースのコレクション クラスの一覧です。  
  
### コレクション テンプレート クラス  
  
|コレクションの内容|配列|表示内容|マップ|  
|---------------|--------|----------|---------|  
|任意の型のオブジェクトのコレクション|`CArray`|`CList`|`CMap`|  
|任意の型のオブジェクトを指すポインターのコレクション|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|  
  
##  <a name="_core_the_collection_classes_not_based_on_templates"></a> テンプレート ベースでないコレクション クラス  
 アプリケーションで MFC 非テンプレート クラスを既に使用している場合は、引き続きそのクラスを使用できます。  ただし、新しいコレクションに対しては、テンプレート ベースのクラスを使用することをお勧めします。  次の表は、テンプレート ベースでない MFC のコレクション クラスの一覧です。  
  
### 非テンプレート コレクション クラス  
  
|配列|表示内容|マップ|  
|--------|----------|---------|  
|`CObArray`|`CObList`|`CMapPtrToWord`|  
|`CByteArray`|`CPtrList`|`CMapPtrToPtr`|  
|`CDWordArray`|`CStringList`|`CMapStringToOb`|  
|`CPtrArray`||`CMapStringToPtr`|  
|`CStringArray`||`CMapStringToString`|  
|`CWordArray`||`CMapWordToOb`|  
|`CUIntArray`||`CMapWordToPtr`|  
  
 「[コレクション クラスの選択に関する推奨事項](../Topic/Recommendations%20for%20Choosing%20a%20Collection%20Class.md)」の表「MFC コレクション クラスの特徴」では、MFC コレクション クラスについて形状以外の次の特徴が示されています。  
  
-   クラスで C\+\+ テンプレートを使用しているか  
  
-   コレクションに格納されている要素をシリアル化できるか  
  
-   コレクションに格納されている要素を診断用にダンプできるか  
  
-   タイプ セーフなコレクションか  
  
### 目的に合ったトピックをクリックしてください  
  
#### 汎用コレクション クラスの操作方法  
  
-   [コレクション クラスの選択に関する推奨事項](../Topic/Recommendations%20for%20Choosing%20a%20Collection%20Class.md)  
  
-   [方法 : タイプ セーフなコレクションを作成する](../mfc/how-to-make-a-type-safe-collection.md)  
  
-   [スタック コレクションとキュー コレクションの作成](../mfc/creating-stack-and-queue-collections.md)  
  
-   [CArray::Add](../Topic/CArray::Add.md)  
  
#### テンプレート ベースのコレクション クラスの操作方法  
  
-   [テンプレート ベースのクラス](../Topic/Template-Based%20Classes.md)  
  
#### コレクションのメンバーへのアクセス \(テンプレート ベース\/非テンプレート\)  
  
-   [コレクションの全メンバーへのアクセス](../mfc/accessing-all-members-of-a-collection.md)  
  
-   [CObject コレクションの全オブジェクトの削除](../Topic/Deleting%20All%20Objects%20in%20a%20CObject%20Collection.md)  
  
## 参照  
 [概念](../mfc/mfc-concepts.md)   
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)