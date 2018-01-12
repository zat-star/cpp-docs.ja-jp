---
title: "未加工の文字列リテラルに変換 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fffbfee4-66ee-42ba-aeb9-df07fb702c51
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12aa512270ecce4564561634f99be9cbf155448a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="convert-to-raw-string-literal"></a>生文字列に変換
**新機能:**リテラルの C++ の未加工の文字列に任意の文字列を有効にすることができます。

****エスケープ文字として処理しないようにするためのエスケープ文字で文字列があります。

**理由:**がわかりにくく、読み取り不可能な文字列に、ダブル エスケープ文字を可能性があります。  読みやすく文字列は、未加工の文字列リテラルを使用します。

**どう：**

1. エスケープされた文字列に変換するテキストやマウスのカーソルを置きます。

   ![強調表示されたコード](images/stringliteral_highlight.png)

1. 次に、次のいずれかの操作を行います。
   * **キーボード**
     * キーを押して**Ctrl + です。** トリガーを**クイック アクションとリファクタリング**メニュー**未加工の文字列リテラルに変換**コンテキスト メニューからです。
   * **マウス**
     * コードを右クリックし、選択、**クイック アクションとリファクタリング**メニュー**未加工の文字列リテラルに変換**コンテキスト メニューからです。
     * をクリックして、![電球](images/bulb.png)クリックし、左余白に表示されるアイコン**未加工の文字列リテラルに変換**コンテキスト メニュー。

1. 文字列のすぐには、未加工文字列リテラルに変換します。  

   ![未加工文字列リテラルの結果](images/stringliteral_result.png)