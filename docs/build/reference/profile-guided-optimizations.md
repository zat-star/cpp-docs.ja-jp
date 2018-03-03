---
title: "プロファイル ガイド付き最適化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- profile-guided optimizations
- optimization, profile-guided [C++]
ms.assetid: 2225c307-d3ae-42c1-8345-a5a959d132dc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f2d72ddda460a88830f7f7692f4c9707fa3101a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="profile-guided-optimizations"></a>ガイド付き最適化のプロファイル
ガイド付き最適化のプロファイルによって出力ファイルを最適化できます。この場合、オプティマイザーは .exe ファイルまたは .dll ファイルのテスト実行データを使用します。 このデータは、稼働環境でのプログラムの実行動作を示します。  
  
 ガイド付き最適化のプロファイルは x86 または [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] のネイティブ ターゲットにのみ使用できます。 ガイド付き最適化のプロファイルは、共通言語ランタイムで実行する出力ファイルでは使用できません。 ネイティブおよびマネージの混合コードを持つアセンブリを生成した場合でも (コンパイル時に**/clr**)、ネイティブ コードだけでプロファイル ガイド付き最適化を使用することはできません。 IDE でこれらのオプション セットを使用してプロジェクトのビルドを試みると、結果としてビルド エラーが発生します。  
  
> [!NOTE]
>  プロファイリングのテスト実行から収集される情報を指定する場合に有効なそれ以外の場合になる最適化がオーバーライドされます**/Ob**、 **/Os**、または**/Ot**です。 詳細については、次を参照してください。 [/Ob (関数のインライン展開)](../../build/reference/ob-inline-function-expansion.md)と[/Os、/Ot (実行速度の優先/os)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)です。  
  
 パフォーマンス ハブと診断ハブで自動化された Visual C++ 用ガイド付き最適化のプロファイル プラグインを使用して、Visual Studio 内の最適化プロセスを簡略化および合理化できます。また、Visual Studio またはコマンド ラインで最適化手順を手動で実行することもできます。 Microsoft では、使いやすいプラグインをお勧めします。 プラグインを取得し、アプリを最適化するために使用する方法については、次を参照してください。[プロファイル ガイド付き最適化のプラグイン](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md)です。  
  
 ガイド付き最適化のプロファイル プラグインとガイド付き最適化のプロファイルの手動操作は、どちらも次の手順に従ってアプリを最適化します。  
  
-   1 つまたは複数のソース コード ファイルをコンパイル[/GL](../../build/reference/gl-whole-program-optimization.md)です。  
  
     ガイド付きプロファイルが実行時の動作をキャプチャして最適化テストを実行している間に、/GL で作成された各モジュールを検証できます。 ガイド付き最適化のプロファイル ビルド内のすべてのモジュールは、/GL を指定してコンパイルする必要はありません。 ただし、/GL を指定してコンパイルされたこれらのモジュールのみがインストルメント化され、ガイド付き最適化のプロファイルに使用できるようになります。  
  
-   使用してリンク[/LTCG](../../build/reference/ltcg-link-time-code-generation.md)と[/GENPROFILE](../../build/reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)です。  
  
     /LTCG および/GENPROFILE の両方を使用して、空の .pgd ファイルを作成します。 テスト実行データが追加された .pgd ファイルは、次のリンク ステップ (最適化イメージの作成) での入力として使用できます。 /GENPROFILE を指定する場合に追加できます。 PGD =`filename`既定以外の名前または .pgd ファイルの場所を指定します。  
  
-   アプリケーションのプロファイリングを行います。  
  
     たびに、プロファイリングされた EXE セッションが終了またはプロファイリングされた DLL がアンロード、 *appname*! # .pgc ファイルを作成します。 .pgc ファイルには、特定のアプリケーションのテスト実行情報が含まれます。 # は他の番号に基づいたにインクリメントされる 1 から始まる番号*appname*!!#.pgc ファイル ディレクトリにします。 テスト実行の結果が目的の最適化のシナリオを示さない場合は、.pgc ファイルを削除できます。  
  
     テストの実行中に、現在開いている .pgc ファイルのクロージャと使用して新しい .pgc ファイルの作成を強制することができます、 [pgosweep](../../build/reference/pgosweep.md) (たとえば、テスト シナリオの最後は、アプリケーションのシャット ダウンと一致しない) 場合は、ユーティリティです。  
  
     アプリケーションのプロファイリングを行うときに、`PogoSafeMode` オプションを使用できます。 このオプションを使用することで、アプリケーションをセーフ モードと高速モードのどちらでプロファイリングするかを指定できます。 これらのモードの詳細については、次を参照してください。 [PogoSafeMode](../../build/reference/pogosafemode.md)です。  
  
-   /LTCG および/USEPROFILE を使用してリンクします。  
  
     /LTCG および/USEPROFILE の両方を使用して、最適化されたイメージを作成します。 このステップでは、.pgd ファイルを入力として使用します。 /USEPROFILE を指定する場合に追加できます。 PGD =`filename`既定以外の名前または .pgd ファイルの場所を指定します。 詳細については、次を参照してください。 [/LTCG](../../build/reference/ltcg-link-time-code-generation.md)です。  
  
 最適化された出力ファイルを作成し、追加のプロファイリングによりさらに最適化されたイメージを作成できるかどうかを後で判断することもできます。 インストルメントされたイメージとその .pgd ファイルを使用できる場合は、追加のテストを実行し、最適化されたイメージをより新しい .pgd ファイルでビルドし直すことができます。  
  
 ガイド付き最適化のプロファイルの一覧を次に示します。  
  
-   **インライン展開**- たとえば、関数 A 関数を B を頻繁に呼び出すことし、関数 B が比較的小さい場合、プロファイル ガイド付き最適化の関数 A. でインライン関数 B が存在する場合  
  
-   **仮想呼び出し推理**-仮想呼び出し、またはその他の呼び出し、関数ポインターを通じて対象が特定の関数が頻繁に、プロファイルのガイド付き最適化が挿入され、条件付きで実行される直接呼び出しを頻繁に対象となる関数直接の呼び出しをインライン展開できます。  
  
-   **レジスタの割り当て**- 向上レジスタの割り当てのプロファイル データの結果を最適化します。  
  
-   **基本ブロックの最適化**-基本ブロックの最適化により、同じ一連のページ (場所) に配置するのには特定のフレーム内で一時的に実行される一般的な実行の基本的な要素です。 これにより使用されるページ数が最小限に抑えられ、メモリのオーバーヘッドが最小限になります。  
  
-   **サイズ/速度の最適化**-プログラムが、多くの時間を費やす関数の速度を最適化できます。  
  
-   **関数のレイアウト**呼び出し先に基づいており、呼び出し元/呼び出し先の動作のプロファイル - 同じ実行パスになる可能性がある関数が同じセクション内に配置します。  
  
-   **条件付き分岐の最適化**- 値プローブをプロファイルのガイド付き最適化の switch ステートメントで指定された値がその他の値よりも頻繁に使用されるかどうかを見つけることができます。  この値は switch ステートメントから取得できます。  また、if ブロックまたは else ブロックのどちらがより頻繁に true になるかに応じて、このどちらかのブロックを最初に置くようにオプティマイザーが if/else を並べ替えることができる場合には、これと同じことを if/else 命令でも行うことができます。  
  
-   **コードの分離**-プロファイル中に呼び出されていないコードは、一連のセクションの末尾に追加される特別なセクションに移動します。 これにより、頻繁に使用されるページからこのセクションが切り離されます。  
  
-   **EH コードの分離**-プロファイル ガイド付き最適化のでは、例外的な条件でのみ、例外が発生することを確認できる場合、的に実行される EH コードを別のセクションに移動多くの場合、ことができます。  
  
-   **メモリの組み込み**-組み込みの拡張によく判断できますを組み込みが頻繁に呼び出される場合は、特定できない場合。 また、組み込みは、移動またはコピーのブロック サイズに基づいて最適化することもできます。  
  
 詳細については、IDE で手動パフォーマンスの最適化をオンまたはコマンド ラインで、次を参照してください。[プロファイル ガイド付き最適化のプラグイン](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [Profile Guided Optimization プラグイン](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md)  
  
 [ガイド付き最適化の手動プロファイル用ツール](../../build/reference/tools-for-manual-profile-guided-optimization.md)  
  
 [方法: 複数の PGO プロファイルを単一のプロファイルにマージする](../../build/reference/how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)  
  
## <a name="see-also"></a>参照  
 [C/C++ のビルド ツール](../../build/reference/c-cpp-build-tools.md)