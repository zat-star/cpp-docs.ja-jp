---
title: "致命的なエラー C1210 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1210
dev_langs:
- C++
helpviewer_keywords:
- C1210
ms.assetid: e2208309-c284-425c-a7e8-48e96e66f35b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c11ed9df47ae7fc607189683b52a35779e485996
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1210"></a>致命的なエラー C1210
/clr:pure および /clr:safe は、インストールされているランタイムのバージョンではサポートされていません  
  
 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。  
  
 C1210 は、コンパイラが現在のリリースであり、共通言語ランタイムが以前のリリースの場合に発生します。  
  
 コンパイラの一部の機能は、ランタイムの以前のバージョンでは動作しない場合があります。  
  
 C1210 を解決するには、コンパイラで使用するバージョンの共通言語ランタイムをインストールしてください。