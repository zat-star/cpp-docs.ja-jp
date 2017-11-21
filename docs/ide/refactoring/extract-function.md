---
title: "Extract 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e31d1249-9705-4511-acbd-9f6fe73bdf2d
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cd91da5296df92103f3d10fd399bd7d53bc57b5b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="extract-function"></a>Extract 関数
**新機能:**独自の関数にコードのフラグメントを変換することができます。

****別の関数から呼び出される必要があるいくつかの関数に既存のコードのフラグメントがあります。  

**理由:**するでしたコピー/貼り付け、そのコードが重複につながることです。  他の関数を自由に呼び出すことができる独自の関数にそのフラグメントをリファクタリングすることをお勧めします。

**どう：**

1. 抽出するコードを強調表示します。

   ![強調表示されたコード](images/extractfunction_highlight.png)

1. 次に、次のいずれかの操作を行います。
   * **キーボード**
     * キーを押して**Ctrl + R**、し**Ctrl + M**です。  選ばれているプロファイルによってキーボード ショートカットが異なる場合があることに注意してください。
     * キーを押して**Ctrl + です。** トリガーに、**クイック アクションとリファクタリング**メニュー**抽出関数 (試験的)**コンテキスト メニューからです。
   * **マウス**
     * 選択**編集 > リファクター > Extract 関数 (試験的)**です。
     * コードを右クリックし、選択、**クイック アクションとリファクタリング**メニュー**抽出関数 (試験的)**コンテキスト メニューからです。
     * をクリックして、![電球](images/bulb.png)クリックし、左余白に表示されるアイコン**抽出関数 (試験的)**コンテキスト メニューからです。

1. **(試験的) 関数、またはメソッドの抽出**ウィンドウで、新しい関数名の入力を配置する、コードが必要とを選択してをクリックして、 **OK**ボタンをクリックします。  

   ![Extract 関数関数](images/extractfunction_dialog.png)

1. 新しい関数が作成されますが、対応するヘッダー ファイル内の関数プロトタイプを指定して、元のコードはその関数を呼び出すに変更されます。

   ![関数の結果を抽出します。](images/extractfunction_result.png)