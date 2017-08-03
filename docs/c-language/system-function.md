---
title: "system 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- system function
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: b504aedc5ad11edf40d7b797529065757dfb58e6
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="system-function"></a>system 関数
**ANSI 4.10.4.5** **system** 関数による文字列の実行の内容とモード  
  
 **system** 関数は、コマンド ラインからではなく、C プログラムから内部オペレーティング システム コマンド、.EXE、.COM (Windows NT の .CMD)、または .BAT ファイルを実行します。  
  
 system 関数は、コマンド インタープリターを探します。これは通常、Windows NT オペレーティング システムでは CMD.EXE、Windows では COMMAND.COM です。 system 関数は、続いてコマンド インタープリターに引数文字列を渡します。  
  
 詳細については、「[system、_wsystem](../c-runtime-library/reference/system-wsystem.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [ライブラリ関数](../c-language/library-functions.md)
