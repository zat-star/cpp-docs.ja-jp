---
title: "/ALIGN (セクション配置) |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/29/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.Alignment
- /align
dev_langs:
- C++
helpviewer_keywords:
- sections, specifying alignment
- ALIGN linker option
- /ALIGN linker option
- -ALIGN linker option
- section alignment
- sections
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ca4572e84c7ad32be2d03a312f7bb7d8a3f3f29
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="align-section-alignment"></a>/ALIGN (セクションの配置)

## <a name="syntax"></a>構文

> **/ALIGN**[**:**_数_]

### <a name="arguments"></a>引数

*数*  
配置の値 (バイト単位)。

## <a name="remarks"></a>コメント

**配置/**オプションは、プログラムのリニア アドレス空間内の各セクションの配置を指定します。 *数*引数をバイト単位で、2 の累乗にする必要があります。 既定では 4 K (4096 です)。 リンカーは、配置は無効なイメージを生成する場合に警告を発行します。

デバイス ドライバーなどのアプリケーションを記述していない場合は、配置を変更する必要があります必要はありません。

Align パラメーターと、特定のセクションのアラインメントを変更することは、 [/section](../../build/reference/section-specify-section-attributes.md)オプション。

指定する配置の値を最大のセクションのアラインメントより小さいにすることはできません。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **リンカー** > **コマンドライン**プロパティ ページ。

1. オプションを入力して、**追加オプション**ボックス。 選択**OK**または**適用**変更を適用します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)  
[リンカー オプション](../../build/reference/linker-options.md)  
