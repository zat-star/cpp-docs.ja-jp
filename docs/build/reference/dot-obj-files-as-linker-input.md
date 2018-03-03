---
title: ".リンカー入力としての Obj ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/29/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- linker [C++], OBJ files as input
- object files, linker output
- OMF object files
- LINK tool [C++], .obj files
- COFF files
- OBJ files as linker input
- .obj files as linker input
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a2896822e97bdbb5ffdf8f869e67beadc1675b7
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="obj-files-as-linker-input"></a>リンカー入力としての .obj ファイル

リンカー ツール (リンクします。EXE) のオブジェクト ファイル形式 COFF (Common) は、.obj ファイルを受け入れます。

## <a name="remarks"></a>コメント

Microsoft では、共通のオブジェクト ファイル形式の完全な説明を提供します。 詳細については、次を参照してください。 [PE 形式](https://msdn.microsoft.com/library/windows/desktop/ms680547)です。

## <a name="unicode-support"></a>Unicode のサポート

Visual Studio 2005 以降では、Microsoft Visual C コンパイラは、ISO/IEC C および C++ 標準で定義された識別子での Unicode 文字をサポートします。 以前のバージョンのコンパイラでは、識別子で ASCII 文字のみをサポートします。 関数、クラス、および静的変数の名前に Unicode をサポートするために、コンパイラとリンカーの Unicode utf-8 エンコードを使用 .obj ファイル内の COFF シンボル。 Utf-8 エンコードは以前のバージョンの Visual Studio によって使用される ASCII エンコーディングと互換性のある upwardly です。

コンパイラとリンカーの詳細については、次を参照してください。[コンパイラおよびリンカーでの Unicode サポート](../../build/reference/unicode-support-in-the-compiler-and-linker.md)です。 Unicode 規格の詳細については、次を参照してください。、 [Unicode](http://go.microsoft.com/fwlink/p/?linkid=37123)組織。

## <a name="see-also"></a>関連項目

[LINK の入力ファイル](../../build/reference/link-input-files.md)  
[リンカー オプション](../../build/reference/linker-options.md)  
[Unicode のサポート](../../text/support-for-unicode.md)  
[コンパイラおよびリンカーでの Unicode のサポート](../../build/reference/unicode-support-in-the-compiler-and-linker.md)  
[Unicode 規格](http://go.microsoft.com/fwlink/p/?linkid=37123)  
[PE 形式](https://msdn.microsoft.com/library/windows/desktop/ms680547)  
