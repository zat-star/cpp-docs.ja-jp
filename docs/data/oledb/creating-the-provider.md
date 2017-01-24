---
title: "プロバイダーの作成 | Microsoft Docs"
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
  - "OLE DB プロバイダー, 作成"
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# プロバイダーの作成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

#### ATL OLE DB プロバイダー ウィザードで OLE DB プロバイダーを作成するには  
  
1.  プロジェクトを右クリックします。  
  
2.  ショートカット メニューの \[追加\] をポイントし、\[クラスの追加\] をクリックします。  
  
3.  \[クラスの追加\] ダイアログ ボックスの \[ATL OLE DB プロバイダー\] アイコンを選択し、\[開く\] をクリックします。  
  
4.  ATL OLE DB プロバイダー ウィザードで、プロバイダーの短縮名を **\[短い名前\]** ボックスに入力します。  以下のトピックでは、短縮名として "MyProvider" を使用しますが、別の名前を使用することもできます。  ほかの名前ボックスは、入力した名前に従って設定されます。  
  
5.  必要に応じて、他の名前ボックスを編集します。  オブジェクト名とファイル名に加えて、以下の項目を編集できます。  
  
    -   \[コクラス\] : COM がプロバイダーを作成するために使用する名前。  
  
    -   \[ProgID\] : プログラム ID。GUID の代わりに使用できる文字列です。  
  
    -   **\[バージョン\]** : バージョンに依存するプログラム ID を生成するために ProgID とコクラスで使用されます。  
  
6.  \[完了\] をクリックします。  
  
## 参照  
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)