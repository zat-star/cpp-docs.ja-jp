---
title: -CLRHEADER |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRHEADER
dev_langs:
- C++
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5896e12d5e3b3b3984884388d11c6380e900d73d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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
  
 共通言語ランタイムのイメージをビルドしたかどうかもプログラムで確認できます。  詳細については、次を参照してください。[する方法: イメージがネイティブ モードまたは CLR 決定](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)です。  
  
 **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 では廃止し、コンパイラの将来のバージョンで削除される予定です。 「純粋」または「安全」にする必要があるコードは、c# に移植する必要があります。 
  
## <a name="see-also"></a>関連項目  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)