---
title: "C++ のセキュリティ推奨事項 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "securitybestpracticesVC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "セキュリティ [C++]"
  - "セキュリティ [C++], 推奨される手順"
  - "Visual C++, セキュリティ"
ms.assetid: 86acaccf-cdb4-4517-bd58-553618e3ec42
caps.latest.revision: 45
caps.handback.revision: 45
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# C++ のセキュリティ推奨事項
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、セキュリティ ツールおよびセキュリティ対策について説明します。  これらを使用しても、アプリケーションを攻撃から完全に防御できるわけではありませんが、攻撃が成功する可能性を低減できます。  
  
## Visual C\+\+ セキュリティ機能  
 Visual C\+\+ コンパイラおよびリンカーには、次のセキュリティ機能が組み込まれています。  
  
 [\/guard \(制御フロー ガードを有効にする\)](../build/reference/guard-enable-control-flow-guard.md)  
 コンパイラは、コンパイル時に間接的な呼び出しのターゲットに関する制御フローを分析し、実行時に、ターゲットを確認するコードを挿入します。  
  
 [\/GS \(バッファーのセキュリティ チェック\)](../Topic/-GS%20\(Buffer%20Security%20Check\).md)  
 利用される危険性がある関数に、オーバーラン検出コードがコンパイラによって挿入されます。  オーバーランが検出されると、実行が停止します。  このオプションの既定値はオンです。  
  
 [\/SAFESEH \(安全な例外ハンドラーがあるイメージ\)](../Topic/-SAFESEH%20\(Image%20has%20Safe%20Exception%20Handlers\).md)  
 各例外ハンドラーのアドレスを格納したテーブルが、リンカーによって出力イメージに含められます。  実行時に、オペレーティング システムはこのテーブルを使用して適切な例外ハンドラーのみが実行されるようにします。  これにより、実行時に悪意のある攻撃を受けて例外ハンドラーが実行されることを回避できます。  このオプションの既定値はオフです。  
  
 [\/NXCOMPAT](../Topic/-NXCOMPAT.md)、[\/NXCOMPAT \(データ実行防止との互換性\)](../build/reference/nxcompat-compatible-with-data-execution-prevention.md)  
 これらのコンパイラ オプションとリンカー オプションを使用すると、データ実行防止 \(DEP: Data Execution Prevention\) との互換性を有効にできます。  DEP は、CPU で非コード ページが実行されないようにします。  
  
 [\/analyze \(コード分析\)](../build/reference/analyze-code-analysis.md)  
 このコンパイラ オプションを使用すると、潜在的なセキュリティ上の問題 \(バッファー オーバーラン、非初期化メモリ、null ポインターの逆参照、メモリ リークなど\) を報告するコード解析がアクティブになります。  このオプションの既定値はオフです。  詳細については、「[C\/C\+\+ のコード分析の概要](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md)」を参照してください。  
  
 [\/DYNAMICBASE \(ASLR \(Address Space Layout Randomization\) の使用\)](../build/reference/dynamicbase-use-address-space-layout-randomization.md)  
 このリンカー オプションにより、実行開始時にメモリ内の個別の場所で読み込むことができる実行可能イメージをビルドできます。  また、このオプションを使用すると、メモリ内のスタックの位置を予測することが非常に難しくなります。  
  
## セキュリティが拡張された CRT  
 C ランタイム ライブラリ \(CRT\) が強化され、セキュリティ上のリスクをもたらす関数 \(チェックが適用されない文字列コピー関数 `strcpy` など\) の安全なバージョンが導入されました。  このようなセキュリティが万全ではない以前の関数は推奨されないため、これらの関数を使用すると、コンパイル時に警告が表示されます。  コンパイル時に警告が表示されないようにするのではなく、これらの CRT 関数の安全なバージョンを使用することをお勧めします。  詳細については、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」を参照してください。  
  
## SafeInt ライブラリ  
 [SafeInt ライブラリ](../windows/safeint-library.md)を利用することで、アプリケーションで算術演算を実行するときに、整数オーバーフローおよびその他の攻撃に利用される可能性のあるエラーが発生するのを防止できます。  `SafeInt` ライブラリには、[SafeInt クラス](../windows/safeint-class.md)、[SafeIntException クラス](../windows/safeintexception-class.md)、および複数の [SafeInt 関数](../windows/safeint-functions.md) が含まれます。  
  
 `SafeInt` クラスを使用することで、整数オーバーフローおよびゼロ除算による攻撃を防止できます。  型が異なる値の比較を処理するために使用できます。  2 種類のエラー処理ポリシーが用意されています。  `SafeInt` クラスの既定のポリシーは、`SafeIntException` クラス例外をスローして、数値演算を完了できない理由を報告することです。  `SafeInt` クラスの 2 番目のポリシーは、プログラムの実行を停止することです。  カスタム ポリシーも定義できます。  
  
 各 `SafeInt` 関数は、対応する 1 つの数値演算で、攻撃に利用される可能性のあるエラーが発生しないようにします。  種類の異なる 2 つのパラメーターを使用できます。これらを同じ型に変換する必要はありません。  複数の数値演算を保護するには、`SafeInt` クラスを使用します。  
  
## チェックを行う反復子  
 チェックを行う反復子は、コンテナー境界を強制します。  既定では、チェックを行う反復子が境界の外側にあると、例外が生成され、プログラムの実行が終了します。  チェックを行う反復子は、**\_SECURE\_SCL\_THROWS** や **\_ITERATOR\_DEBUG\_LEVEL** など、プリプロセッサ定義に割り当てられた値に基づき他のレベルの応答を提供します。  たとえば、**\_ITERATOR\_DEBUG\_LEVEL\=2** の場合、チェックを行う反復子は、デバッグ モードで正確性を包括的にチェックします。この機能は、アサートを使用することで利用できます。  詳細については、「[チェックを行う反復子](../standard-library/checked-iterators.md)」を参照してください。  
  
## マネージ コードのコード分析  
 マネージ コードのコード分析は FxCop とも呼ばれ、.NET Framework デザイン ガイドラインに準拠するためにアセンブリをチェックします。  FxCop は各アセンブリ内のコードとメタデータを解析して、次の点に不備がないかどうかを検証します。  
  
-   ライブラリ デザイン  
  
-   ローカリゼーション  
  
-   名前付け規則  
  
-   パフォーマンス  
  
-   セキュリティ  
  
## Windows アプリケーション検証ツール  
 アプリケーション検証ツール \(AppVerifier\) は、アプリケーションの互換性、安定性、およびセキュリティ上の問題を特定するのに役立ちます。  
  
 AppVerifier は、アプリケーションがどのようにオペレーティング システムを使用するのかを監視します。  AppVerifier は、アプリケーションの実行中に、ファイル システム、レジストリ、メモリ、および API を監視し、AppVerifier がカバーしない問題については、ソース コードの修正を推奨します。  
  
 AppVerifier は、次の用途で使用できます。  
  
-   一般的なプログラミング上の誤りが原因で発生する潜在的なアプリケーションの互換性エラーがないかどうかをテストします。  
  
-   アプリケーションにメモリ関連の問題がないかどうかを調べます。  
  
-   アプリケーションの潜在的なセキュリティ上の問題を特定します。  
  
 AppVerifier は、TechNet Web サイトの「[アプリケーションの互換性](http://go.microsoft.com/fwlink/?LinkId=91277)」から入手できる Application Compatibility Toolkit に含まれています。  
  
## .NET Framework のセキュリティ機能  
 「[NIB: Configuring Security Policy](http://msdn.microsoft.com/ja-jp/0f130bcd-1bba-4346-b231-0bcca7dab1a4)」で、.NET Framework セキュリティ ポリシーを調整するためのガイドラインおよびツールについて説明しています。  
  
## Windows ユーザー アカウント  
 Administrators グループに属する Windows ユーザー アカウントを使用すると、開発者とユーザー \(機能拡張により\) がセキュリティ上の危険にさらされます。  詳細については、「[ユーザー グループのメンバーとしての実行](../top/running-as-a-member-of-the-users-group.md)」、および「[ユーザー アカウント制御 \(UAC: User Account Control\) がアプリケーションに与える影響](../Topic/How%20User%20Account%20Control%20\(UAC\)%20Affects%20Your%20Application.md)」を参照してください。  
  
## 参照  
 <xref:System.Security>   
 [セキュリティ](../Topic/Security%20in%20the%20.NET%20Framework.md)   
 [ユーザー アカウント制御 \(UAC: User Account Control\) がアプリケーションに与える影響](../Topic/How%20User%20Account%20Control%20\(UAC\)%20Affects%20Your%20Application.md)