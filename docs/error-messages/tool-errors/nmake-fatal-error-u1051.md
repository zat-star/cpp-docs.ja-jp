---
title: "NMAKE の致命的なエラー U1051 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1051
dev_langs: C++
helpviewer_keywords: U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 93c109bf723b3c4cf08e998a715fe8f6f33be466
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE の致命的なエラー U1051
メモリ不足  
  
 (Nmake の) は、メイクファイルが大きすぎるか複雑なために、仮想メモリを含め、メモリ不足になりました。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  ディスクの領域を解放します。  
  
2.  Windows NT のページング ファイルまたは Windows のスワップ ファイルのサイズを増やします。  
  
3.  メイクファイルの一部が使用されている場合のみ、メイクファイルを個別のファイルに分割するか使用して**!IF**プリプロセス ディレクティブ (nmake の) を処理する必要がある量を制限します。 **!IF**ディレクティブには、 **!IF**、 `!IFDEF`、 **!IFNDEF**、 **!ELSE IF**、 **!ELSE** `IFDEF`、および**!ELSE** `IFNDEF`です。