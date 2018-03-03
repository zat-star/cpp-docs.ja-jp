---
title: "コマンドラインの警告 D9026 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D9026
dev_langs:
- C++
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9127ad1887d476e5460798f806c2db1ff3144de3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-warning-d9026"></a>コマンド ラインの警告 D9026
オプションはコマンドライン全体に適用します。  
  
 オプションは、ファイル名の指定後、コマンドで指定されました。 オプションは、前に、ファイルに適用されました。  
  
 たとえば、コマンドで  
  
```  
CL verdi.c /G5 puccini.c  
```  
  
 /G4 デフォルトではありません、/G5 オプションを使用して、VERDI.c というファイルがコンパイルされます。  
  
 この動作は VERDI.c で結果として得られる、ファイル名の前に指定されたオプションを使用してコンパイル/G4 と異なりコンパイル/G5 を使用してのみに適用されるいくつか以前のバージョンの場合と異なります。