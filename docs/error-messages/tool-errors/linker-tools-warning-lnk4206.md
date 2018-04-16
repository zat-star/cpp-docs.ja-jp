---
title: "リンカー ツールの警告 LNK4206 |Microsoft ドキュメント"
ms.date: 12/05/2017
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4206
dev_langs:
- C++
helpviewer_keywords:
- LNK4206
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cd13ac59aefa074db869f0502743c7a49d23082c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4206"></a>リンカー ツールの警告 LNK4206

> プリコンパイル済みの型情報が見つかりませんでした。'*filename*' リンクしていないか上書き; オブジェクトをリンク デバッグ情報がありません

*Filename*を使用してコンパイルされたオブジェクト ファイル[/Yc](../../build/reference/yc-create-precompiled-header-file.md)が LINK コマンドで指定されていないか、または上書きされました。

この警告の一般的なシナリオは、その .obj をコードからのシンボル参照がないと/Yc でコンパイルされた .obj ファイルが、ライブラリの場合です。  その場合は、リンカーはありません (またはも参照してください) 使用 .obj ファイル。  このような状況で、コードを再コンパイルして使用する必要があります[/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md)を使用してコンパイルされたオブジェクトの[/Yu](../../build/reference/yu-use-precompiled-header-file.md)です。