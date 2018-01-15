---
title: "Windows XP 用プログラムの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ff80109c1f3a5e03ecb85406cdaea24804f96783
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="configuring-programs-for-windows-xp"></a>Windows XP 用プログラムの構成
Visual Studio では、複数のプラットフォーム ツールセットをサポートするためには、オペレーティング システムと、既定のツールセットでサポートされていないランタイム ライブラリをターゲット設定できます。 たとえば、プラットフォーム ツールセットを切り替えることによって行うこともできます、c++ 11、c++ 14、および Visual Studio での Visual C コンパイラでサポートされている c++ 17 言語拡張機能をターゲットとするアプリを作成する[!INCLUDE[winxp](../build/includes/winxp_md.md)]と[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]です。 またバイナリ互換性のあるレガシ コードを維持するために以前のプラットフォーム ツールセットを使用し、引き続き Visual Studio IDE の最新の機能の利用できます。  
  
> [!NOTE]
>  使用している場合[!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)]、インストールする必要があります[!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)]のプラットフォーム ツールセットのサポートを追加する更新プログラム 4[!INCLUDE[winxp](../build/includes/winxp_md.md)]と[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]です。 ダウンロードしてインストールのコピー[!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)]更新プログラム 4 を参照してください[Microsoft Visual Studio Express 2012 for Windows Desktop](http://go.microsoft.com/fwlink/p/?linkid=265464) Microsoft ダウンロード センターにします。 インストールし、 [Visual Studio 2012 Update 4](http://go.microsoft.com/fwlink/p/?linkid=335900) v110_xp プラットフォーム ツールセットを取得します。 インストール後に、Windows Update を使用して最新のソフトウェア更新プログラムを受け取ります。  
  
## <a name="windows-xp-targeting-experience"></a>Windows XP 対応のエクスペリエンス  
 Visual Studio に含まれている Windows XP プラットフォーム ツールセットのバージョンは、 [!INCLUDE[win7](../build/includes/win7_md.md)] SDK に含まれていた[!INCLUDE[vs_dev10_long](../build/includes/vs_dev10_long_md.md)]は、最新の C++ コンパイラを使用します。 また、これは、プロジェクトのプロパティを適切な既定値に構成します。たとえば、下位レベルへの対応用の、互換性のあるリンカーの仕様などです。 Windows XP プラットフォーム ツールセットを使用して作成されたデスクトップ アプリで実行する Windows のみ[!INCLUDE[winxp](../build/includes/winxp_md.md)]と[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]、それらのアプリを最新の Windows オペレーティング システムで実行できるもします。  
  
#### <a name="to-target-windows-xp"></a>Windows XP に対応するには  
  
1.  **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、**[プロパティ]** を選択します。  
  
2.  **プロパティ ページ**ダイアログ ボックスで、プロジェクトの**構成プロパティ**、**全般**、設定、**プラットフォーム ツールセット**必要な Windows XP ツールセットのプロパティです。 たとえば、選択**Visual Studio 2015 - Windows XP (v140_xp)**コードを作成する[!INCLUDE[winxp](../build/includes/winxp_md.md)]と[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]Microsoft Visual C 2015 コンパイラを使用しています。  
  
### <a name="c-runtime-support"></a>C++ ランタイムのサポート  
 Windows XP プラットフォーム ツールセット、C ランタイム ライブラリ (CRT)、C++ 標準ライブラリ、アクティブ テンプレート ライブラリ (ATL)、同時実行ランタイム ライブラリ (ConCRT)、並列パターン ライブラリ (PPL)、Microsoft Foundation Class ライブラリ (MFC)、および C++ AMP (C++ と大規模なプログラミングを加速) ライブラリのランタイム サポートは含ま[!INCLUDE[winxp](../build/includes/winxp_md.md)]と[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]です。 最小のサポートされているバージョンは、これらのオペレーティング システムの[!INCLUDE[winxp](../build/includes/winxp_md.md)]x86、Service Pack 3 (SP3) [!INCLUDE[winxp](../build/includes/winxp_md.md)] x64 の場合、Service Pack 2 (SP2) および[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]x86 と x64 の両方の Service Pack 2 (SP2) です。  
  
 これらのライブラリは、ターゲットに応じた、Visual Studio によってインストールされているプラットフォームのツールセットでサポートされます。  
  
|ライブラリ|Windows デスクトップ アプリを対象とする既定のプラットフォーム ツールセット|[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリを対象とする既定のプラットフォーム ツールセット|[!INCLUDE[winxp](../build/includes/winxp_md.md)]、[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] を対象とする Windows XP プラットフォーム ツールセット|  
|-------------|-------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|  
|CRT|X|X|x|  
|C++ 標準ライブラリ|x|X|X|  
|[ATL]|X|X|X|  
|ConCRT/PPL|X|X|X|  
|MFC|X||X|  
|C++ AMP|X|X||  
  
> [!NOTE]
>  C++/CLI で作成され、.NET Framework 4 を対象とするアプリは、[!INCLUDE[winxp](../build/includes/winxp_md.md)] および [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] で動作します。  
  
### <a name="differences-between-the-toolsets"></a>ツールセットの間の相違点  
 プラットフォームとライブラリのサポートの違いにより、Windows XP プラットフォーム ツールセットを使用するアプリの開発のエクスペリエンスは既定の Visual Studio のプラットフォーム ツールセットを使用するアプリの場合ほど完全でないです。  
  
-   **C++ 言語の機能**  
  
     実装された C++ 言語機能だけ[!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)]v110_xp プラットフォーム ツールセットを使用するアプリではサポートされています。 C++ 言語機能だけがで実装された[!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]v120_xp のプラットフォーム ツールセットを使用するアプリではサポートされています。 Visual Studio は、以前のプラットフォーム ツールセットを使用してビルドするときに、対応するコンパイラを使用します。 そのバージョンのコンパイラで実装されたその他の C++ 言語の機能を活用するために、最新の Windows XP プラットフォーム ツールセットを使用します。  
  
-   **リモート デバッグ**  
  
     Visual Studio 用のリモート ツールが上でリモート デバッグをサポートしていない[!INCLUDE[winxp](../build/includes/winxp_md.md)]または[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]です。 実行されているときに、アプリをデバッグする[!INCLUDE[winxp](../build/includes/winxp_md.md)]または[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]、古いバージョンの Visual Studio からデバッガーを使用してローカルまたはリモートでデバッグすることができます。 これと似ているのが Windows Vista のアプリのデバッグのエクスペリエンスであり、これはプラットフォーム ツールセットのランタイム ターゲットですが、リモートのデバッグ ターゲットではありません。  
  
-   **スタティック分析**  
  
     Windows XP のプラットフォーム ツールセットは、[!INCLUDE[win7](../build/includes/win7_md.md)] SDK の SAL 注釈とランタイム ライブラリに互換性がないため、静的分析をサポートしていません。 [!INCLUDE[winxp](../build/includes/winxp_md.md)] または [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] をサポートするアプリの静的分析を実行する場合は、既定のプラットフォーム ツールセットに対応するようソリューションを一時的に切り替え、分析を実行してから Windows XP のプラットフォーム ツールセットに戻ってアプリをビルドすることができます。  
  
-   **DirectX グラフィックスのデバッグ**  
  
     グラフィックス デバッガーは Direct3D 9 API をサポートしていないため、[!INCLUDE[winxp](../build/includes/winxp_md.md)] または [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] で Direct3D を使用するアプリのデバッグにこれを利用することはできません。 ただし、アプリが Direct3D 10 または Direct3D 11 の API を使用する代替のレンダラーを実装する場合、これらの API を使用する場合の問題の診断にグラフィックス デバッガーを利用できます。  
  
-   **HLSL の構築**  
  
     既定では、Windows XP ツールセットでは HLSL のソース コード ファイルはコンパイルされません。 HLSL ファイルをコンパイルするには、June 2010 DirectX SDK をダウンロードしてインストールし、プロジェクトの VC ディレクトリに含めるように設定します。 詳細については、次を参照してください。、"DirectX SDK が登録されないインクルード/ライブラリ パスを Visual Studio 2010"のセクション、 [June 2010 DirectX SDK ダウンロード ページ](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812)です。