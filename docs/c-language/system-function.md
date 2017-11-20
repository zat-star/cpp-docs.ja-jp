---
title: "system 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: system function
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 965cca807ddbe9f0eb31144f75a7e3c6e4a80e77
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="system-function"></a>system 関数
**ANSI 4.10.4.5** **system** 関数による文字列の実行の内容とモード  
  
 **system** 関数は、コマンド ラインからではなく、C プログラムから内部オペレーティング システム コマンド、.EXE、.COM (Windows NT の .CMD)、または .BAT ファイルを実行します。  
  
 system 関数は、コマンド インタープリターを探します。これは通常、Windows NT オペレーティング システムでは CMD.EXE、Windows では COMMAND.COM です。 system 関数は、続いてコマンド インタープリターに引数文字列を渡します。  
  
 詳細については、「[system、_wsystem](../c-runtime-library/reference/system-wsystem.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [ライブラリ関数](../c-language/library-functions.md)