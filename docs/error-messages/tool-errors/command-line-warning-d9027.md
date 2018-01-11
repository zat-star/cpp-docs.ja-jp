---
title: "コマンドラインの警告 D9027 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D9027
dev_langs: C++
helpviewer_keywords: D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2769eb5f78cb1d5bdd6749e65429d83b69a2807b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-warning-d9027"></a>コマンド ラインの警告 D9027
ソース ファイル '\<filename >' は無視されます  
  
 CL.exe には、入力ソース ファイルが無視されます。  
  
 この警告は、/Fo オプションと/c オプションを使用して、コマンド ラインで出力ファイル名の間をスペースで可能性があります。 例:  
  
```  
cl /c /Fo output.obj input.c   
```  
  
 /Fo 間にスペースがあるため、 `output.obj`、CL.exe は`output.obj`入力ファイルの名前として。 問題を解決するには、スペースを削除します。  
  
```  
cl /c /Fooutput.obj input.c   
```