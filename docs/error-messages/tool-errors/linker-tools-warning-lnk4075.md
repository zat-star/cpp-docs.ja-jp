---
title: "リンカー ツールの警告 LNK4075 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4075
dev_langs:
- C++
helpviewer_keywords:
- LNK4075
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
caps.latest.revision: 8
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
translationtype: Machine Translation
ms.sourcegitcommit: 9dee257bec0f09bd729bf10c4a1468ecb20dfa61
ms.openlocfilehash: 84dea754a1d2268c92e703dd04b0169ccc258ab3
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4075"></a>リンカー ツールの警告 LNK4075
原因は、"option2"仕様「オプション&1;」を無視します。  
  
 2 番目のオプションは、1 つ目をオーバーライドします。  
  
 相互に排他的なリンカー オプションが指定されます。  リンカー オプションを確認します。  リンカーのオプションが指定されているプロジェクトをビルドしている方法によって異なります。  
  
-   開発環境を作成している場合は、プロジェクトでは、[リンカー] プロパティ ページで参照し、両方のリンカー オプションが指定されています。  参照してください[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)の詳細。  
  
-   コマンドラインでビルドする場合が指定されているリンカー オプションを検討します。  
  
-   ビルド スクリプトを構築する場合は、これらのリンカー オプションが指定されているスクリプトを参照します。  
  
 見つかった場合は、相互に排他的なリンカー オプションが指定されている、リンカー オプションのいずれかを削除します。  
  
 具体例を示します。  
  
-   コンパイルされたモジュールをリンクする場合は**/ZI**、/EDITANDCONTINUE ものではありません/EDITANDCONTINUE とを/OPT:REF や/OPT:ICF、/incremental:no と、コンパイルされたモジュールと呼ばれる内部リンカー オプションが含まれて、LNK4075 が表示されます。  参照してください[/Z7、/Zi、/ZI (デバッグ情報の形式)](../../build/reference/z7-zi-zi-debug-information-format.md)の詳細。
