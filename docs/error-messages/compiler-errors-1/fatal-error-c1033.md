---
title: "致命的なエラー C1033 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1033
dev_langs:
- C++
helpviewer_keywords:
- C1033
ms.assetid: 09976c03-8450-4cf7-8b43-1b91c2c2b9f9
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a0c9c67d23f2d0b957fb3e43844245029efedc64
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1033"></a>致命的なエラー C1033
プログラム データベースの pdb ファイルを開くことができません。  
  
 このエラーは、ディスク エラーが発生することができます。  
  
 Visual C .NET 2002 では、ユーザー ロケール設定しなければなりません正しくファイル名 (またはファイル名へのディレクトリ パス) に MBCS 文字が含まれている場合。 システム ロケールを設定するだけでは不十分です。MBCS 文字を処理するようにユーザー ロケールを設定する必要があります。  
  
 詳細については、次を参照してください。 [http://support.microsoft.com/default.aspx?scid=kb;en-us;246007](http://support.microsoft.com/default.aspx?scid=kb;en-us;246007)です。
