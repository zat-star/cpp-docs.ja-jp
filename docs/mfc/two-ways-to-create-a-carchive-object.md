---
title: "CArchive オブジェクトを作成する 2 つの方法 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CArchive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive クラス, 閉じる (CArchive オブジェクトを)"
  - "CArchive クラス, コンストラクター"
  - "CArchive オブジェクト"
  - "CArchive オブジェクト, 閉じる"
  - "データ ストレージ [C++], CArchive クラス"
  - "I/O [MFC], 作成 (CArchive オブジェクトを)"
  - "シリアル化 [C++], CArchive クラス"
  - "ストレージ [C++], CArchive クラス"
ms.assetid: aefa28ce-b55c-40dc-9e42-5f038030985d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CArchive オブジェクトを作成する 2 つの方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CArchive` オブジェクトを作成するには 2 とおりの方法があります。:  
  
-   [フレームワークによる CArchive オブジェクトの暗黙の作成](#_core_implicit_creation_of_a_carchive_object_via_the_framework)  
  
-   [CArchive オブジェクトが明示的に作成](#_core_explicit_creation_of_a_carchive_object)  
  
##  <a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a> フレームワークによる CArchive オブジェクトの暗黙の作成  
 共通のが最も簡単な方法は、ドキュメントの `CArchive` オブジェクトを保存、保存の代わりとして作成し、メニューのファイルを開くようにするフレームワークで行います。  
  
 アプリケーションのユーザーが、ファイル メニューの名前を付けて保存コマンドを実行すると、ここでフレームワークの動作です:  
  
1.  **\[名前を付けて保存\]** ダイアログ ボックスが表示され、ユーザーからファイル名を取得します。  
  
2.  `CFile` オブジェクトとしてユーザーが指定するファイルを開きます。  
  
3.  この `CFile` へのポインターを格納します。`CArchive` オブジェクトを作成します。  `CArchive` オブジェクトの作成では、フレームワークは「ストア」および「Load」に対してモード \(のシリアル化する書き込み\)、\(逆シリアル化するなど\) に設定します。  
  
4.  `Serialize` 関数を **CDocument**\-、`CArchive` オブジェクトへの参照を渡す派生クラスで定義された呼び出します。  
  
 ドキュメントの `Serialize` 関数はこれまで説明した、`CArchive` オブジェクトにデータを書き込みます。  次に `Serialize` 関数から制御が返されるときに、フレームワークは `CArchive` オブジェクトと `CFile` オブジェクトを破棄します。  
  
 したがって、フレームワークがドキュメントの `CArchive` オブジェクトを作成しようとしている必要があるのは、アーカイブに対する読み書きドキュメントの `Serialize` 関数を実装することだけです。  また、`CObject`の `Serialize` \-ドキュメントの `Serialize` 関数が直接的または間接的にシリアル化派生オブジェクトを実装しなければなりません。  
  
##  <a name="_core_explicit_creation_of_a_carchive_object"></a> CArchive オブジェクトが明示的に作成  
 フレームワークによるドキュメントのシリアル化のほかに `CArchive` オブジェクトを必要とする場合に、他の機会が与えられます。  たとえば、`CSharedFile` オブジェクトによって表されるクリップボードとの間でデータをシリアル化する場合があります。  または、フレームワークに用意されているものとは異なるファイルを格納するためのユーザー インターフェイスを使用することもできます。  この場合、明示的に `CArchive` オブジェクトを作成できます。  次の手順を使用してこれをフレームワークが同じ方法で行われます。  
  
#### 明示的に CArchive オブジェクトを作成するには  
  
1.  `CFile`から派生される `CFile` オブジェクトまたはオブジェクトを構築します。  
  
2.  次の例に示すように `CArchive`のコンストラクターへの `CFile` オブジェクトを、渡します。:  
  
     [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/CPP/two-ways-to-create-a-carchive-object_1.cpp)]  
  
     `CArchive` のコンストラクターへの 2 番目の引数は、アーカイブ ファイルから、または保存またはデータの読み込みに使用するかどうかを指定する列挙値です。  オブジェクトの `Serialize` 関数はアーカイブ オブジェクトを `IsStoring` 関数を呼び出すことでこの状態をチェックします。  
  
 終了する格納したり、`CArchive` へのデータの読み込みを格納すると、ファイルを閉じます。  `CArchive` \(および `CFile`\) オブジェクトが自動的にアーカイブ \(およびファイル\) を閉じますが、明示的にエラーからの回復を簡単にするため、推奨される方法です。  エラー処理の詳細については、記事 [例外: 例外をキャッチするか、または削除します。](../mfc/exceptions-catching-and-deleting-exceptions.md)を参照します。  
  
#### CArchive オブジェクトを閉じます。  
  
1.  次の例に `CArchive` オブジェクトを閉じる方法を示しています。:  
  
     [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/CPP/two-ways-to-create-a-carchive-object_2.cpp)]  
  
## 参照  
 [シリアル化 : オブジェクトのシリアル化](../Topic/Serialization:%20Serializing%20an%20Object.md)