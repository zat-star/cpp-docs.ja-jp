---
title: "致命的なエラー C1510 |Microsoft ドキュメント"
ms.custom: 
ms.date: 04/11/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1510
dev_langs:
- C++
helpviewer_keywords:
- C1510
ms.assetid: 150c827f-9514-41a9-8d7e-82f820749bcb
caps.latest.revision: 1
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 05aee6ce5cba18d0517a134eb217a149098beb6e
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1510"></a>致命的なエラー C1510
言語リソース clui.dll を開くことができません  
  
 コンパイラは、言語リソース DLL を読み込むことができません。  
  
この問題の 2 つの一般的な原因があります。 32 ビットのコンパイラおよびツールを使用する場合は、大きなプロジェクトのリンク中に 2 GB を超えるメモリを使用するには、このエラーを参照してください可能性があります。 ソリューションでは、64 ビットの Windows システムでは、64 ビットのネイティブを使用してまたはクロス コンパイラと、コードを生成するツールです。 これは、大規模なメモリの空き 64 ビット アプリを利用します。 場合は、32 ビット システムで実行しているために、32 ビット コンパイラを使用する必要があります、場合によっては向上することが 3 GB にリンカーに使用可能なメモリの量。 詳細については、次を参照してください。 [4 ギガバイト チューニング。 BCDEdit と Boot.ini](https://msdn.microsoft.com/library/vs/alm/bb613473(v=vs.85).aspx)と[BCDEdit/set increaseuserva](https://msdn.microsoft.com/library/ff542202.aspx)コマンド。  

その他の一般的な原因は、Visual Studio インストールに壊れているか不完全です。 ここでは、修復または Visual Studio を再インストールをもう一度インストーラーを実行します。  
  
