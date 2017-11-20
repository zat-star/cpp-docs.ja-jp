---
title: "リソース コンパイラ エラー RC2144 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC2144
dev_langs: C++
helpviewer_keywords: RC2144
ms.assetid: 1b3ff39a-92cd-4a04-b1a3-b1fa6a805813
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 828a64ebe618bef5c6929ca3591551aec9e91e81
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="resource-compiler-error-rc2144"></a>リソース コンパイラ エラー RC2144
主言語 ID が数字ではありません。  
  
 主言語 ID は 16 進数の言語 ID にする必要があります。 参照してください[言語および国/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)で、*ランタイム ライブラリ リファレンス*有効な言語 Id の一覧についてはします。  
  
 このエラーは、ツールを使用して、.RC ファイルにリソースを追加してから削除した場合にも発生することがあります。 この問題を解決するには、.RC ファイルをテキスト エディターで開き、使用されていないすべてのリソースを手動でクリーンアップします。