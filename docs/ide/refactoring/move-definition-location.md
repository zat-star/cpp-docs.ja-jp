---
title: "定義の場所に移動 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6d507ac-c61e-4da2-95c8-d504b42e2520
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 838f3d01f5e6d8612948304b80b79cf9c7cb4720
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="move-definition-location"></a>定義の場所の移動
**新機能:**すぐに対応するヘッダー ファイルに関数定義を移動することができます。

****ヘッダー ファイルに移動する関数があります。  

**理由:**関数を手動で移動する可能性がありますが、この機能は、自動的に移動、必要な場合は、ヘッダー ファイルを作成します。

**どう：**

1. この関数は、移動するテキストまたはマウス カーソルを置きます。

   ![強調表示されたコード](images/movedefinition_highlight.png)

1. 次に、次のいずれかの操作を行います。
   * **キーボード**
     * キーを押して**Ctrl + です。** トリガーを**クイック アクションとリファクタリング**メニュー**定義の場所を移動**コンテキスト メニューからです。
   * **マウス**
     * 右クリックし、選択、**クイック アクションとリファクタリング**メニュー**定義の場所を移動**コンテキスト メニュー。

1. 関数は、ポップアップ プレビュー ウィンドウに表示されますが、対応するヘッダー ファイルに移動されます。  ヘッダー ファイルが存在しない場合がも作成され、プロジェクトに配置します。

   ![宣言を作成/定義の結果](images/movedefinition_result.png)
