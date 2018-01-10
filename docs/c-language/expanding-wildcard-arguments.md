---
title: "ワイルドカード引数の展開 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- asterisk wildcard
- question mark, wildcard
- expanding wildcard arguments
- wildcards, expanding
ms.assetid: 80a11c4b-0199-420e-a342-cf1d803be5bc
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f710cc1695579bf1a6f873229c347966888bc745
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="expanding-wildcard-arguments"></a>ワイルドカード引数の展開
**Microsoft 固有の仕様**  
  
 C プログラムを実行する際、コマンド ラインのファイル名引数とパス引数の指定に、2 つのワイルドカード (疑問符 (?) およびアスタリスク (*)) のいずれかを使用できます。  
  
 既定では、ワイルドカードはコマンドラインの引数では展開されません。 setargv.obj または wsetargv.obj ファイルとリンクしてワイルドカードを展開し、標準の引数ベクターの `argv` 読み込みルーチンをワイルドカードを展開するバージョンと置き換えることができます。 プログラムが `main` 関数を使用している場合は、setargv.obj とリンクします。プログラムが `wmain` 関数を使用している場合は、wsetargv.obj とリンクします。これら両方の動作は同等です。  
  
 setargv.obj または wsetargv.obj とリンクするには、 **/link** オプションを使用します。 例:  
  
 **cl example.c /link setargv.obj**  
  
 ワイルドカードはオペレーティング システム コマンドと同じように展開されます (ワイルドカードの使用経験がない場合は、オペレーティング システムのユーザー ガイドを参照)。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [リンク オプション](../c-runtime-library/link-options.md)   
 [main 関数とプログラム実行](../c-language/main-function-and-program-execution.md)