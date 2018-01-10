---
title: "インライン ファイルのテキストを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dcc27a303e9d03d2e899a76703bcfae5abfd0c04
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="creating-inline-file-text"></a>インライン ファイルのテキストの作成
インライン ファイルは、一時的または永続的です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      inlinetext  
.  
.  
.  
<<[KEEP | NOKEEP]  
```  
  
## <a name="remarks"></a>コメント  
 指定*inlinetext*コマンドの後に最初の行にします。 二重山かっこの末尾をマーク (<<) は別々 の行の先頭にします。 ファイルがすべて含まれています*inlinetext*区切りの角かっこの前にします。 *Inlinetext*マクロの展開と置換がないディレクティブまたはメイクファイルのコメントを持つことができます。 スペース、タブ、および改行文字として扱われます。  
  
 一時ファイルは、セッションの期間が存在し、他のコマンドで再利用することができます。 指定**保持**(nmake の) セッションの後にファイルを保持する閉じる山かっこの後に、名前のないファイルが生成されたファイル名でディスクに保存されます。 指定**NOKEEP**または一時ファイルのものがありません。 **保持**と**NOKEEP**大文字小文字は区別されません。  
  
## <a name="see-also"></a>参照  
 [メイクファイルのインライン ファイル](../build/inline-files-in-a-makefile.md)