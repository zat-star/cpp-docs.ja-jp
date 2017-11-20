---
title: "プロパティ (Visual C) を追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interfaces, adding properties
- properties [C++], adding to interfaces
ms.assetid: 37bd4db7-efd3-4faa-87ad-64902ed16a36
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d8cc313fd677d56e00c883bf1c32d8154edcce8b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="adding-a-property-visual-c"></a>プロパティの追加 (Visual C++)
使用することができます、[プロパティの追加ウィザード](../ide/names-add-property-wizard.md)プロジェクト内のインターフェイスにメソッドを追加します。  
  
### <a name="to-add-a-property-to-your-object"></a>オブジェクトにプロパティを追加するには  
  
1.  [クラス ビュー](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)プロパティを追加するインターフェイスの名前を右クリックします。  
  
    > [!NOTE]
    >  ディスパッチ インターフェイスは、プロジェクトに属性が、しない限りが、[ライブラリ] ノード内に入れ子にするプロパティを追加することもできます。  
  
2.  ショートカット メニューをクリックして**追加**、クリックして**プロパティの追加**です。  
  
3.  [プロパティの追加ウィザード](../ide/names-add-property-wizard.md)プロパティの作成に情報を提供します。  
  
4.  内のプロパティの任意のインターフェイス定義言語 (IDL) の設定を指定、 [IDL 属性](../ide/idl-attributes-add-property-wizard.md)ウィザードのページです。  
  
5.  をクリックして**完了**プロパティを追加します。  
  
 **取得**と`Put`プロパティのメソッドがクラス ビューで定義されているインターフェイスの下の 2 つのアイコンとして表示されます。 .Idl ファイルのプロパティの宣言を表示するいずれかのアイコンをダブルクリックすることができます。  
  
-   ATL のインターフェイスで、**取得**と**Put**関数は、.cpp ファイルに追加され、これらの関数への参照は、.h ファイルに追加されます。  
  
-   選択した場合は、MFC ディスパッチ インターフェイス**メンバー変数**実装の型としては、それを実装するクラスにメソッドと変数を追加します。 します。 選択した場合**Get/set メソッド**実装の種類として、2 つのメソッドが実装するクラスに追加されます。  
  
## <a name="see-also"></a>関連項目  
 [COM インターフェイスの作成](../ide/creating-a-com-interface-visual-cpp.md)   
 [COM インターフェイスの編集](../ide/editing-a-com-interface.md)   
 [コンポーネント オブジェクト モデル](http://msdn.microsoft.com/library/windows/desktop/ms694363)   
 [インターフェイス ポインターとインターフェイス](http://msdn.microsoft.com/library/windows/desktop/ms688484)