---
title: "マルチ スレッド プログラムの問題を回避 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- multithreading [C++], troubleshooting
- errors [C++], multithreaded programs
- threading [C++], troubleshooting
- troubleshooting [C++], multithreading
ms.assetid: 06cc231d-bb5a-409d-8bd3-676c9e2a8c5b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 546f5b5daa88578fc7dd062018257f0929bc0cff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="avoiding-problem-areas-with-multithread-programs"></a>マルチスレッド プログラムの問題を回避する方法
作成する、リンク、またはマルチ スレッドの C プログラムの実行で発生する可能性がいくつかの問題があります。 いくつかの一般的な問題については、次の表で説明します。 (MFC の観点から説明については、次を参照してください[マルチ スレッド: プログラミングのヒント](../parallel/multithreading-programming-tips.md)。)。  
  
|問題|考えられる原因|  
|-------------|--------------------|  
|プログラムによる保護違反を示すメッセージ ボックスが表示されます。|多くの Win32 プログラミング エラーには、保護違反が発生します。 保護違反の一般的な原因は、間接割り当て null ポインターへのデータです。 属していないメモリにアクセスしようとして、プログラムでこの結果、ため保護違反となります。<br /><br /> 保護違反の原因を検出する簡単な方法では、デバッグ情報を使用してプログラムをコンパイルし、Visual C 環境で、デバッガーを実行します。 保護違反が発生すると Windows デバッガーに制御を転送する問題が発生した行にカーソルが配置されています。|  
|プログラムには、多数のコンパイルとリンク エラーが生成されます。|コンパイラの警告レベルを最も高い値のいずれかに設定し、警告メッセージを heeding で多くの潜在的な問題を回避できます。 レベル 3 またはレベル 4 の警告レベルのオプションを使用して、意図しないデータ変換、関数プロトタイプの不足、および ANSI 以外の機能の使用を検出できます。|  
  
## <a name="see-also"></a>参照  
 [C と Win32 を使用するマルチスレッド](../parallel/multithreading-with-c-and-win32.md)