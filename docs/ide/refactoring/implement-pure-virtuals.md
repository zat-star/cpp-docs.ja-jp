---
title: "純粋仮想を実装して |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea9b4719-34a3-474a-b4ec-05b1859f80f1
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f311c2e5832754bfd785084b9aa930b5dbe43845
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2018
---
# <a name="implement-pure-virtuals"></a>純粋仮想を実装します。
**新機能:**直ちにクラスですべての純粋仮想メソッドを実装するために必要なコードを生成することができます。 

**条件:**純粋仮想関数を持つクラスから継承します。  

**理由:**すべて純粋仮想関数を 1 つずつを手動で実装でしたが、この機能では、すべてのメソッド署名を自動的に作成されます。

**方法:**

1. 基本クラスの純粋仮想関数を実装するクラスにテキストまたはマウス カーソルを置きます。

   ![強調表示されたコード](images/virtuals_highlight.png)

1. 次に、以下のいずれかを実行します。
   * **キーボード**
     * **Ctrl + .** キーを押して、 トリガーに、**クイック アクションとリファクタリング**メニュー**クラスのすべての純粋仮想を実装する*ClassName*'** 、コンテキスト メニューから場所*ClassName*選択したクラスの名前を指定します。
   * **マウス**
     * 右クリックし、選択、**クイック アクションとリファクタリング**メニュー**クラスのすべての純粋仮想を実装する*ClassName*'**コンテキスト メニューから場所*ClassName*選択したクラスの名前を指定します。

1. 純粋仮想メソッドのシグネチャは、自動的に作成された、実装する準備完了になります。

   ![純粋仮想の実装結果します。](images/virtuals_result.png)
