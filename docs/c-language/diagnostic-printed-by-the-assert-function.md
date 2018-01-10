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
ms.workload: cplusplus
ms.openlocfilehash: 243956f1d85b07b5d5b810ebfd112b2cbfe16242
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="diagnostic-printed-by-the-assert-function"></a>assert 関数によって出力される診断
**ANSI 4.2** **assert** 関数が印刷する診断と関数の終了動作  
  
 **assert** 関数は診断メッセージを表示し、式が false (0) の場合に **abort** ルーチンを呼び出します。 診断メッセージにフォームがあります  
  
 **アサーションに失敗しました**: *expression***, ファイル** *filename***, 行** *linenumber*  
  
 ここで、filename はソース ファイルの名前であり、linenumber はソース ファイルで失敗したアサーションの行番号です。 式が true の場合 (ゼロ以外)、アクションは発生しません。  
  
## <a name="see-also"></a>参照  
 [ライブラリ関数](../c-language/library-functions.md)