---
title: ".リンカー入力としての Obj ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- linker [C++], OBJ files as input
- object files, linker output
- OMF object files
- LINK tool [C++], .obj files
- COFF files
- OBJ files as linker input
- .obj files as linker input
ms.assetid: 3028e423-8b10-4972-8eb4-6e9ae58f0a26
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ca8346f9ff29d097450eda4d8bfbfee7f7a3f522
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="obj-files-as-linker-input"></a>リンカー入力としての .obj ファイル
リンカー ツール (リンクします。EXE) のオブジェクト ファイル形式 COFF (Common) は、.obj ファイルを受け入れます。  
  
## <a name="remarks"></a>コメント  
 Microsoft では、共通のオブジェクト ファイル形式を定義するドキュメントのダウンロードを提供します。 詳細については、8.1 またはそれ以降のバージョンをダウンロード、 [Microsoft ポータブル実行可能ファイルと一般的なオブジェクト ファイル形式の仕様](http://go.microsoft.com/fwlink/?LinkId=93292)です。  
  
## <a name="unicode-support"></a>Unicode のサポート  
 Visual Studio 2005 以降では、Microsoft Visual C コンパイラは、ISO/IEC C および C++ 標準で定義された識別子での Unicode 文字をサポートします。 以前のバージョンのコンパイラでは、識別子で ASCII 文字のみをサポートします。 関数、クラス、および静的変数の名前に Unicode をサポートするために、コンパイラとリンカーの Unicode utf-8 エンコードを使用 .obj ファイル内の COFF シンボル。 Utf-8 エンコードは以前のバージョンの Visual Studio によって使用される ASCII エンコーディングと互換性のある upwardly です。  
  
 コンパイラとリンカーの詳細については、次を参照してください。[コンパイラおよびリンカーでの Unicode サポート](../../build/reference/unicode-support-in-the-compiler-and-linker.md)です。 Unicode 規格の詳細については、次を参照してください。、 [Unicode](http://go.microsoft.com/fwlink/?LinkId=37123)組織。  
  
## <a name="see-also"></a>関連項目  
 [LINK の入力ファイル](../../build/reference/link-input-files.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [Unicode のサポート](../../text/support-for-unicode.md)   
 [コンパイラおよびリンカーで Unicode のサポート](../../build/reference/unicode-support-in-the-compiler-and-linker.md)   
 [Unicode 規格](http://go.microsoft.com/fwlink/?LinkId=37123)   
 [一般的なオブジェクト ファイル形式の仕様](http://go.microsoft.com/fwlink/?LinkId=93292)