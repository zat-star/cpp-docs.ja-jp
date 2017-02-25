---
title: "CObject からのクラスの派生 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObject クラス, 派生"
  - "CObject クラス, 派生 (シリアル化できるクラスを)"
  - "DECLARE_DYNAMIC マクロ"
  - "DECLARE_DYNCREATE マクロ"
  - "DECLARE_SERIAL マクロ"
  - "派生クラス, CObject から"
  - "マクロ [C++], シリアル化"
  - "シリアル化 [C++], マクロ"
ms.assetid: 5ea4ea41-08b5-4bd8-b247-c5de8c152a27
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# CObject からのクラスの派生
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは [CObject](../Topic/CObject%20Class.md)からクラスを派生するために必要な最小限の手順について説明します。  他の `CObject` クラスのトピックでは、シリアル化と診断デバッグ サポート `CObject` などの特定の機能を利用するために必要な手順について説明します。  
  
 `CObject`の説明では、用語は「ファイル」インターフェイスを実装し、「file」がよく使用されます。  インターフェイス ファイル \(通常はヘッダー ファイルと、呼び出されます。H ファイル\) はクラスを使用するために必要なクラス宣言およびそのほかの情報が含まれています。  実装ファイル \(.cpp ファイル\) クラス定義を、クラスのメンバー関数を実装するコードが含まれています。  たとえば、A というクラスは `CPerson`という、通常 PERSON.H インターフェイスという名前のファイルを作成し、実装ファイルは PERSON.CPP という名前です。  ただし、アプリケーション間で共有する、小さなクラスには、単一の .cpp ファイルにインターフェイスと実装を組み合わせると、簡単です。  
  
 `CObject`からクラスを派生する場合は、関数の 4 レベルから選択できます:  
  
-   基本機能: ランタイム クラス情報またはシリアル化のサポートは、診断メモリ管理は含まれません。  
  
-   ランタイム クラス情報をサポートする基本機能。  
  
-   ランタイム クラス情報、および動的生成をサポートする基本機能。  
  
-   ランタイム クラス情報、動的生成およびシリアル化をサポートする基本機能。  
  
 基本クラスとして後で動作する再利用 \(、\) 用に設計されたクラスは、後続のシリアル化のニーズが予測される場合、ランタイム クラスのサポートとシリアル化のサポートを含める必要があります。  
  
 ユーザーが `CObject`から派生するクラスの宣言と実装で特定の宣言と実装のマクロを使用することにより、機能のレベルを選択します。  
  
 次の表は、サポート シリアル化、およびランタイム クラス情報への使用されるマクロの関係を示しています。  
  
### シリアル化、およびランタイム情報に使用するマクロ  
  
|使用されるマクロ|CObject::IsKindOf|CRuntimeClass::<br /><br /> CreateObject|CArchive::operator\>\><br /><br /> CArchive::operator\<\<|  
|--------------|-----------------------|--------------------------------------|-------------------------------------------------------|  
|`CObject` の基本的な機能|No|No|No|  
|`DECLARE_DYNAMIC`|Yes|No|No|  
|`DECLARE_DYNCREATE`|Yes|Yes|No|  
|`DECLARE_SERIAL`|Yes|Yes|Yes|  
  
#### CObject の基本的な機能を使用するには  
  
1.  `CObject` からクラスを派生するために標準 C\+\+ 構文を使用すると、`CObject`の派生クラスから\)。  
  
     次の例では、最も単純な場合、`CObject`からクラスの派生クラスを示しています。:  
  
     [!code-cpp[NVC_MFCCObjectSample#1](../mfc/codesnippet/CPP/deriving-a-class-from-cobject_1.h)]  
  
 しかし、新しいクラスの詳細を処理するために `CObject` のメンバー関数の一部をオーバーライドすることもできます。  たとえば、通常はクラスのコンテンツにデバッグ出力を表示するに `CObject` の `Dump` 関数をオーバーライドする必要があります。  `Dump`をオーバーライドする方法の詳細については [診断: オブジェクトの内容をダンプ](http://msdn.microsoft.com/ja-jp/727855b1-5a83-44bd-9fe3-f1d535584b59)記事を参照してください。  また、クラス オブジェクトのデータ メンバーの整合性を検証するためにカスタマイズしたテストを提供するように `CObject` の `AssertValid` 関数をオーバーライドする必要があります。  `AssertValid`をオーバーライドする方法の詳細については [MFC ASSERT\_VALID および CObject::AssertValid](http://msdn.microsoft.com/ja-jp/7654fb75-9e9a-499a-8165-0a96faf2d5e6)を参照してください。  
  
 記事 [機能の指定](../mfc/specifying-levels-of-functionality.md) はランタイム クラス情報、動的オブジェクトの作成とシリアル化機能などの他のレベルを指定する方法について説明します。  
  
## 参照  
 [CObject の使い方](../mfc/using-cobject.md)