---
title: EDITBIN リファレンス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- editbin
dev_langs:
- C++
helpviewer_keywords:
- binary data, editing
- object files, modifying
- EDITBIN program
- COFF files, editing
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0ff9c0c58498361764dcc1b6c454c9b629d9bed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="editbin-reference"></a>EDITBIN リファレンス
Microsoft COFF Binary ファイル エディター (EDITBIN です。EXE) では、オブジェクト ファイル形式 COFF (Common) のバイナリ ファイルを変更します。 EDITBIN を使用して、オブジェクト ファイル、実行可能ファイル、およびダイナミック リンク ライブラリ (DLL) を変更することができます。  
  
> [!NOTE]
>  このツールは、[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] コマンド プロンプトからのみ開始できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。  
  
 EDITBIN はにより生成されるファイルで使用するため使用できません、 [/GL](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。 /GL で生成されたバイナリ ファイルに変更を加えるには、再コンパイルとリンクで行う必要があります。  
  
-   [EDITBIN コマンドライン](../../build/reference/editbin-command-line.md)  
  
-   [EDITBIN オプション](../../build/reference/editbin-options.md)  
  
## <a name="see-also"></a>参照  
 [C/C++ のビルド ツール](../../build/reference/c-cpp-build-tools.md)