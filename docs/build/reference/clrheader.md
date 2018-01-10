---
title: "-CLRHEADER |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /CLRHEADER
dev_langs: C++
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d8ab1617cffd7560ab47d69f7304df0c76b661eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="clrheader"></a>/CLRHEADER
```  
/CLRHEADER file  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 `file`  
 ビルドされたイメージ ファイル[/clr](../../build/reference/clr-common-language-runtime-compilation.md)です。  
  
## <a name="remarks"></a>コメント  
 このオプションは、任意のマネージ プログラムで使用される .NET ヘッダー情報を表示します。 出力は、.NET ヘッダーとヘッダー内のセクションのバイト単位のサイズと場所を示しています。  
  
 のみ、 [/HEADERS](../../build/reference/headers.md) DUMPBIN オプションはにより生成されるファイルで使用できるよう、 [/GL](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。  
  
 /CLRHEADER は/clr でコンパイルされたファイルで使用する場合があります、 **clr ヘッダー。** dumpbin 出力」セクション。  値**フラグ**どの/clr オプションを使用したことを示します。  
  
-   0--/clr (イメージは、ネイティブ コードを含めることがあります)。  
  
-   1--/clr:safe (イメージは MSIL だけ、任意の CLR プラットフォームで実行して検証可能な可能性があります)。  
  
-   3--/clr: 純粋な (イメージは MSIL だけですが、x86 上で実行することのみプラットフォーム)。  
  
 共通言語ランタイムのイメージをビルドしたかどうかもプログラムで確認できます。  詳細については、次を参照してください。[する方法: イメージがネイティブ モードまたは CLR 決定](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)です。  
  
 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。  
  
## <a name="see-also"></a>参照  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)