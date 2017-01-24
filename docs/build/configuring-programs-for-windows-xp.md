---
title: "Windows XP 用 C++ 11 プログラムの構成 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
caps.latest.revision: 14
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Windows XP 用 C++ 11 プログラムの構成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] は複数のプラットフォーム ツールセットをサポートしているため、既定のツールセットでサポートされていないオペレーティング システムとランタイム ライブラリに対応することができます。  たとえば、C\+\+11 言語の拡張、コンパイラ、ライブラリや、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] で実装されているその他の機能を使用して、[!INCLUDE[winxp](../build/includes/winxp_md.md)] と [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] に対応するアプリを作成できます。  以前のプラットフォーム ツールセットを使用して、バイナリ互換性のあるレガシ コードを保守しながら、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] IDE の最新の機能も利用できます。  
  
> [!NOTE]
>  [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] および [!INCLUDE[winxp](../build/includes/winxp_md.md)] のプラットフォーム ツールセットのサポートを [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] に追加するには、[!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] 更新プログラム 4 をインストールする必要があります。  [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] 更新プログラム 4 をダウンロードしてインストールするには、 Microsoft ダウンロード センターの「[Microsoft Visual Studio Express 2012 for Windows Desktop](http://go.microsoft.com/fwlink/?LinkID=265464)」を参照してください。  次に、[Visual Studio 2012 更新プログラム 4](http://go.microsoft.com/fwlink/?LinkID=335900) をインストールして、v110\_xp プラットフォーム ツールセットを入手します。  インストール後に、Windows Update を使用して最新のソフトウェア更新プログラムを受け取ります。  
  
## Windows XP 対応のエクスペリエンス  
 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] に含まれている Windows XP プラットフォーム ツールセットは、[!INCLUDE[win7](../build/includes/win7_md.md)] に含まれていた [!INCLUDE[vs_dev10_long](../build/includes/vs_dev10_long_md.md)] SDK のバージョンですが、最新の C\+\+ コンパイラを使用しています。  また、これは、プロジェクトのプロパティを適切な既定値に構成します。たとえば、下位レベルへの対応用の、互換性のあるリンカーの仕様などです。  Windows XP プラットフォーム ツールセットを使用して作成された Windows デスクトップ アプリのみが [!INCLUDE[winxp](../build/includes/winxp_md.md)] と [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] で動作しますが、これらのアプリは、Windows Vista、[!INCLUDE[win7](../build/includes/win7_md.md)]、[!INCLUDE[winsvr08](../build/includes/winsvr08_md.md)]、[!INCLUDE[win8](../build/includes/win8_md.md)]、[!INCLUDE[winserver8](../build/includes/winserver8_md.md)] など、最近のオペレーティング システムでも動作します。  
  
#### Windows XP に対応するには  
  
1.  **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、**\[プロパティ\]** をクリックします。  
  
2.  プロジェクトの \[**プロパティ ページ**\] ダイアログ ボックスの \[**構成プロパティ**\]、\[**全般**\] で、\[**プラットフォーム ツールセット**\] プロパティを必要な Windows XP ツールセットに設定します。  たとえば、\[**Visual Studio 2012 – Windows XP \(v110\_xp\)**\] を選択して、Microsoft Visual C 2012 再頒布可能ライブラリとバイナリ互換性のあるコードを作成します。  
  
### C\+\+ ランタイムのサポート  
 Windows XP のプラットフォーム ツールセットの他に、C ランタイム ライブラリ \(CRT\)、標準テンプレート ライブラリ \(STL\)、Active Template Library \(ATL\)、同時実行ランタイム ライブラリ \(ConCRT\)、並列パターン ライブラリ \(PPL\)、Microsoft Foundation Class ライブラリ \(MFC\)、および C\+\+ AMP \(C\+\+ Accelerated Massive Programming\) ライブラリに [!INCLUDE[winxp](../build/includes/winxp_md.md)] と [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] のランタイム サポートが含まれます。  これらのオペレーティング システムでサポートされるバージョンは、x86 用 [!INCLUDE[winxp](../build/includes/winxp_md.md)] Service Pack 3 \(SP3\)、x64 用 [!INCLUDE[winxp](../build/includes/winxp_md.md)] Service Pack 2 \(SP2\)、および x86 と x64 用 [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] Service Pack 2 \(SP2\) です。  
  
 これらのライブラリは [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] によってインストールされているプラットフォーム ツールセットによりサポートされますが、サポート状況はターゲットに応じて異なります。  
  
|ライブラリ|Windows デスクトップ アプリを対象とする既定のプラットフォーム ツールセット|[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] アプリを対象とする既定のプラットフォーム ツールセット|[!INCLUDE[winxp](../build/includes/winxp_md.md)]、[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] を対象とする Windows XP プラットフォーム ツールセット|  
|-----------|------------------------------------------------|---------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|  
|CRT|X|X|X|  
|STL|X|X|X|  
|\[ATL\]|X|X|X|  
|ConCRT\/PPL|X|X|X|  
|MFC|X||X|  
|C\+\+ AMP|X|X||  
  
> [!NOTE]
>  C\+\+\/CLI で作成され、.NET Framework 4 を対象とするアプリは、[!INCLUDE[winxp](../build/includes/winxp_md.md)] および [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] で動作します。  
  
### ツールセットの間の相違点  
 プラットフォームとライブラリのサポートの違いにより、Windows XP のプラットフォーム ツールセットを使用するアプリの開発のエクスペリエンスは、既定の [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] プラットフォーム ツールセットを使用するアプリの場合ほどに完全ではありません。  
  
-   **C\+\+ 言語の機能**  
  
     v110\_xp のプラットフォーム ツールセットを使用するアプリでサポートされているのは、[!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] に実装されている C\+\+ 11 言語機能だけです。  v120\_xp のプラットフォーム ツールセットを使用するアプリでサポートされているのは、[!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] に実装されている C\+\+ 11 の機能だけです。  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] は、以前のプラットフォーム ツールセットを使用してビルドするときに、対応するコンパイラを使用します。  そのバージョンに実装されている C\+\+11 の追加機能を利用するには、より新しい Windows XP のプラットフォーム ツールセットを使用します。  
  
-   **リモート デバッグ**  
  
     Remote Tools for [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] は、[!INCLUDE[winxp](../build/includes/winxp_md.md)] または [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] のリモート デバッグをサポートしません。  [!INCLUDE[winxp](../build/includes/winxp_md.md)] または [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] で実行しているときにアプリをデバッグするために、以前のバージョンの [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] のデバッガーを使用して、ローカルまたはリモートでデバッグすることができます。  これと似ているのが Windows Vista のアプリのデバッグのエクスペリエンスであり、これはプラットフォーム ツールセットのランタイム ターゲットですが、リモートのデバッグ ターゲットではありません。  
  
-   **静的分析**  
  
     Windows XP のプラットフォーム ツールセットは、[!INCLUDE[win7](../build/includes/win7_md.md)] SDK の SAL 注釈とランタイム ライブラリに互換性がないため、静的分析をサポートしていません。  [!INCLUDE[winxp](../build/includes/winxp_md.md)] または [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] をサポートするアプリの静的分析を実行する場合は、既定のプラットフォーム ツールセットに対応するようソリューションを一時的に切り替え、分析を実行してから Windows XP のプラットフォーム ツールセットに戻ってアプリをビルドすることができます。  
  
-   **DirectX グラフィックスのデバッグ**  
  
     グラフィックス デバッガーは Direct3D 9 API をサポートしていないため、[!INCLUDE[winxp](../build/includes/winxp_md.md)] または [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] で Direct3D を使用するアプリのデバッグにこれを利用することはできません。  ただし、アプリが Direct3D 10 または Direct3D 11 の API を使用する代替のレンダラーを実装する場合、これらの API を使用する場合の問題の診断にグラフィックス デバッガーを利用できます。  
  
-   **HLSL の構築**  
  
     既定では、Windows XP ツールセットでは HLSL のソース コード ファイルはコンパイルされません。  HLSL ファイルをコンパイルするには、June 2010 DirectX SDK をダウンロードしてインストールし、プロジェクトの VC ディレクトリに含めるように設定します。  詳細については、[June 2010 DirectX SDK ダウンロード ページ](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812)の「DirectX SDK はインクルード\/ライブラリ パスを Visual Studio 2010 に登録しない」セクションを参照してください。