---
title: "リンカー ツールの警告 LNK4204 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4204
dev_langs:
- C++
helpviewer_keywords:
- LNK4204
ms.assetid: 14adda20-0cbe-407b-90f6-9f81c93530e2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f9b2d9611192fe4afe01d178ac3af5fcc8ccc42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4204"></a>リンカー ツールの警告 LNK4204
'filename' は参照するモジュールのデバッグ情報がありません。オブジェクトをリンク デバッグ情報がありません。  
  
 .Pdb ファイルには、不適切な署名があります。 リンカーはデバッグ情報なしオブジェクトをリンクし続けます。 オブジェクト ファイルを使用して、再コンパイルすることができます、 [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)オプション。  
  
 LNK4204 は、存在しなくなったファイルを参照して、ライブラリ内のオブジェクトの場合に発生することができます。 これは発生した可能性、ソリューションをリビルドするときに例を示します。オブジェクト ファイルは削除され、コンパイル エラーにより再構築されること可能性があります。 この場合、いずれかのコンパイル時に**/Z7**、または**/Fd**、1 つのファイルごとにライブラリ (は既定の .pdb ファイル名ではありません) を参照するオブジェクトを更新します。  詳細については、「[/Fd (プログラム データベース ファイル名)](../../build/reference/fd-program-database-file-name.md)」を参照してください。  ソース管理システムが更新されるたびに、ライブラリと .pdb ファイルを保存することを確認します。