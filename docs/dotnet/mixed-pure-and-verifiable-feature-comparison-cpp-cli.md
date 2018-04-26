---
title: 混合、純粋、および検証可能な機能の比較 (C + + CLI) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- safe assemblies [C++], vs. pure
- mixed assemblies [C++], vs. pure
- safe assemblies [C++], vs. mixed
- pure MSIL [C++]
- verifiable assemblies [C++]
- pure MSIL [C++], vs. safe
- pure MSIL [C++], vs. mixed
- pure MSIL [C++], compared to mixed and safe
- verifiable assemblies [C++], vs. mixed
- mixed assemblies [C++], vs. safe
- verifiable assemblies [C++], vs. pure
- pure assemblies [C++]
- safe assemblies [C++]
- mixed assemblies [C++]
ms.assetid: 3f7a82ba-0e69-4927-ba0c-fbc3160e4394
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d4ac2356fbe12af53890e8159484b89150b60945
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="mixed-pure-and-verifiable-feature-comparison-ccli"></a>混合、純粋、および確認可能の各機能の比較 (C++/CLI)
このトピックは、別の機能を比較 **/clr**コンパイル モード。 詳細については、「[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で非推奨とされています。  
  
## <a name="feature-comparison"></a>機能の比較  
  
|機能|混合 (/clr)|純粋 (/clr:pure)|安全な (//clr:safe)|関連情報|  
|-------------|---------------------|-------------------------|-------------------------|-------------------------|  
|CRT ライブラリ|サポートされています。|非推奨||[カテゴリ別の universal C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)|  
|MFC/ATL|サポートされています。|||[MFC デスクトップ アプリケーション](../mfc/mfc-desktop-applications.md) &#124; [クラスの概要](../atl/atl-class-overview.md)|  
|アンマネージ関数|サポートされています。|||[混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)|  
|アンマネージ データ|サポートされています。|非推奨||[純粋なコードと検証可能なコード (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)|  
|アンマネージ関数から呼び出すこと|サポートされています。||||  
|アンマネージ関数の呼び出しをサポートしています|サポートされています。|非推奨|非推奨|[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)|  
|リフレクションをサポートします。|のみの Dll|非推奨|非推奨|[リフレクションの問題 (C++/CLI)](../dotnet/reflection-cpp-cli.md)|  
  
## <a name="see-also"></a>関連項目  
 [純粋なコードと検証可能なコード (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)