---
title: "assert 関数によって出力される診断 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d6e5ea4e5f8bae3fda190ac7a7136035aea0c948
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="diagnostic-printed-by-the-assert-function"></a>assert 関数によって出力される診断
**ANSI 4.2** **assert** 関数が印刷する診断と関数の終了動作  
  
 **assert** 関数は診断メッセージを表示し、式が false (0) の場合に **abort** ルーチンを呼び出します。 診断メッセージにフォームがあります  
  
 **アサーションに失敗しました**: *expression***, ファイル** *filename***, 行** *linenumber*  
  
 ここで、filename はソース ファイルの名前であり、linenumber はソース ファイルで失敗したアサーションの行番号です。 式が true の場合 (ゼロ以外)、アクションは発生しません。  
  
## <a name="see-also"></a>関連項目  
 [ライブラリ関数](../c-language/library-functions.md)