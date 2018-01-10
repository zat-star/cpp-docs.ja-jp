---
title: "混在アセンブリのライブラリのサポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- msvcm90[d].dll
- mixed assemblies [C++], library support
- msvcmrt[d].lib
- libraries [C++], mixed assemblies
ms.assetid: 1229595c-9e9d-414d-b018-b4e4c727576d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9b3bc50416eceac64c134a31a4d7384e33db69b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="library-support-for-mixed-assemblies"></a>混在アセンブリのためのライブラリ サポート
Visual C、C++ 標準ライブラリ (CRT)、共通ランタイム ライブラリの使用をサポートする ATL、およびでコンパイルされたアプリケーションの MFC [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)です。 これにより、既存のアプリケーションも .NET Framework の機能を使用するためにこれらのライブラリを使用できます。  
  
 このサポートには、次の新しい DLL とインポート ライブラリが導入されています。  
  
-   /Clr でコンパイルする場合は、.lib を Msvcmrt [d] です。 混在アセンブリへのリンクをこのライブラリをインポートします。  
  
-   Msvcm90 [d] .dll および Msvcurt [d] .lib/clr でコンパイルする場合: 純粋なです。 DLL は C 実行時間 (CRT) の管理のサポートを提供する、混在アセンブリは、グローバル アセンブリ キャッシュ (GAC) にインストールされているマネージ アセンブリの一部です。 このインポート ライブラリと最終的に msvcm90.dll とバインドへのリンクを純粋なアセンブリ。  
  
 このサポートは、関連するいくつかの利点を提供します。  
  
-   CRT および C++ 標準ライブラリは、両方混合コードと純粋なコードを使用できます。 提供されている C++ 標準ライブラリ、CRT は検証不能です。最終的には、呼び出しはネイティブ コードから使用するとも同じ CRT および C++ 標準ライブラリにルーティングされます。  
  
-   純粋なおよび混合イメージ内の統合された例外処理を修正します。  
  
-   純粋なおよび混合イメージ内の C++ の変数の静的な初期化します。  
  
-   マネージ コードで、AppDomain ごとと、プロセスごとの変数をサポートします。  
  
-   Visual Studio 2003 以前のバージョンでコンパイルされた混在モード Dll に適用されるローダー ロックに関する問題を解決します。  
  
 さらに、このサポートには、次の制限事項が表示されます。  
  
-   CRT DLL モデルのみがサポートされている (/clr または/clr:pure でコンパイルされたコードの両方: 純粋な)。  
  
-   (ため、すべてのオブジェクトは、純粋なイメージで純粋である必要があります)、それらのオブジェクトが、Visual C ライブラリを使用する場合は、1 つのイメージの純粋と混合オブジェクトを混在させることはできません。 これを行う場合は、リンク時のエラーが発生します。  
  
 以前のバージョンで動作する保証はありません、現在のバージョンに、共通言語ランタイム (CLR) を更新してください。 CLR のバージョンではこれらの変更でビルドされたコードが実行されない 1.x です。  
  
## <a name="see-also"></a>参照  
 [混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)