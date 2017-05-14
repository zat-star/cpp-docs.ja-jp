---
title: "致命的なエラー c1052 など |Microsoft ドキュメント"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1052
dev_langs:
- C++
helpviewer_keywords:
- C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
caps.latest.revision: 0
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
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: f3ab91c1c79b822a4d9a33fb0ab5fbd88146fff0
ms.contentlocale: ja-jp
ms.lasthandoff: 05/10/2017

---
# <a name="fatal-error-c1052"></a>致命的なエラー c1052 など
プログラム データベース ファイルでは、'*filename*'、;/DEBUG:fastlink のリンカーによって生成されたコンパイラできませんこのような PDB ファイルを更新; してください削除するかまたは/Fd を使用して、別の PDB ファイル名を指定。  
  
コンパイラはリンカーによって生成された同じプログラム データベース (PDB) ファイルを更新できないときに、 [/DEBUG:fastlink](../../build/reference/debug-generate-debug-info.md)オプションを指定します。 通常、コンパイラによって生成された PDB ファイルと、リンカーによって生成された PDB ファイルは、異なる名前を付けます。 同じ名前を使用する設定されている場合は、このエラーは発生できます。  
  
この問題を修正するには、前に、もう一度、コンパイルするか、コンパイラによって生成されたファイルとリンカーによって生成された PDB ファイルに異なる名前を作成することができますに PDB ファイルを明示的に削除できます。 コマンドラインでコンパイラにより生成された別の PDB ファイル名を作成するには、使用、 [/Fd](../../build/reference/fd-program-database-file-name.md)オプション。 IDE では、別の PDB ファイル名を生成するには、開く、**プロパティ ページ**で、プロジェクトのダイアログ ボックス、**構成プロパティ**、 **C/C++**、**出力ファイル** ページで、設定、**プログラム データベース ファイル名**プロパティです。 このプロパティは、既定では、`$(IntDir)vc$(PlatformToolsetVersion).pdb`です。 代わりに、リンカーによって生成された PDB ファイル名を設定することができます。 開く、**プロパティ ページ**で、プロジェクトのダイアログ ボックス、**構成プロパティ**、**リンカー**、**デバッグ** ページで、設定、**プログラム データベース ファイルの生成**プロパティです。 既定では、このプロパティは `$(OutDir)$(TargetName).pdb` に設定されています。  

