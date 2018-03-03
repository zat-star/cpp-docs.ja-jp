---
title: "NMAKE の致命的なエラー U1045 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1045
dev_langs:
- C++
helpviewer_keywords:
- U1045
ms.assetid: dc70d162-14b9-4107-9237-7514044d72e3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cdd9fb3d0bcee20e1952cea6444f586a9117365a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1045"></a>NMAKE の致命的なエラー U1045
起動に失敗しました : メッセージ  
  
 NMAKE によって呼び出されたプログラムまたはコマンドが、特定の理由により失敗しました。 NMAKE がコンパイラやリンカーなどの別のプログラムを呼び出したときに、呼び出しが失敗したか、または呼び出されたプログラムによってエラーが返された可能性があります。 このメッセージは、エラーを報告するために使用されます。  
  
 この問題を解決するには、まず、エラーの原因を判別します。 NMAKE によって報告されるコマンドを使用する[/N](../../build/nmake-options.md)オプション環境設定を確認して、コマンドラインで NMAKE によって実行される操作を繰り返します。