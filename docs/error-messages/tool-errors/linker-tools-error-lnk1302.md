---
title: "リンカ ツール エラー LNK1302 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1302
dev_langs:
- C++
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a5b9201608d6d457288c7ade9376147da08bcb9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1302"></a>リンカ ツール エラー LNK1302
安全な .netmodule; のリンクのみをサポートします。ファイル .netmodule にリンクすることができません。  
  
 .Netmodule (でコンパイルされた**/LN**) が、ユーザーで MSIL のリンクを起動するために、リンカーに渡されました。  C++ モジュールと MSIL にコンパイルする場合のリンクに対して有効では、 **/clr:safe**です。  
  
 このエラーを修正するコンパイル時に**/clr:safe** MSIL リンクすると、有効にするにまたはパス、 **/clr**または**/clr: 純粋な**モジュールの代わりにリンカーを .obj ファイル。  
  
 詳細については、次のトピックを参照してください。  
  
-   [/LN (MSIL モジュールの作成)](../../build/reference/ln-create-msil-module.md)  
  
-   [.netmodule ファイル (リンカー入力)](../../build/reference/netmodule-files-as-linker-input.md)