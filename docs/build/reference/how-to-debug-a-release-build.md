---
title: "方法: リリース ビルドをデバッグ |Microsoft ドキュメント"
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
- debugging [C++], release builds
- release builds, debugging
ms.assetid: d333e4d1-4e6c-4384-84a9-cb549702da25
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 31113d9a5935536ac10b22c7b5f5af27b0d29970
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-debug-a-release-build"></a>方法 : リリース ビルドをデバッグする
アプリケーションのリリース ビルドをデバッグすることができます。  
  
### <a name="to-debug-a-release-build"></a>リリース ビルドをデバッグするには  
  
1.  開く、**プロパティ ページ**プロジェクトのダイアログ ボックス。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、 **C/C++**ノード。 設定**デバッグ情報の形式**に[C7 互換 (/Z7)](../../build/reference/z7-zi-zi-debug-information-format.md)または**プログラム データベース (/Zi)**です。  
  
3.  展開**リンカー**  をクリックし、**全般**ノード。 設定**インクリメンタル リンクを有効にする**に[いいえ (//INCREMENTAL:NO)](../../build/reference/incremental-link-incrementally.md)です。  
  
4.  選択、**デバッグ**ノード。 設定**デバッグ情報の生成**に[はい (/debug)](../../build/reference/debug-generate-debug-info.md)です。  
  
5.  選択、**最適化**ノード。 設定**参照**に[/opt:ref による](../../build/reference/opt-optimizations.md)と**COMDAT の圧縮を有効にする**に[/OPT:ICF](../../build/reference/opt-optimizations.md)です。  
  
6.  リリース ビルドのアプリケーションをデバッグできます。 障害が発生したが見つかるまで、問題、ステップ実行、コード (または使用ジャスト イン タイムのデバッグ) を検索し、不正確なパラメーターまたはコードを確認しています。  
  
     アプリケーション デバッグ ビルドでは動作では、リリース ビルドに失敗した場合は、コンパイラの最適化のいずれかの可能性があるを公開する、ソース コードの欠陥です。 問題を特定するには、ファイルと、問題の原因となった、最適化が見つかるまで、各ソース コード ファイルの選択の最適化を無効にします。 (処理の時間を短縮するには、ファイルを 2 つのグループに分割、1 つのグループでの最適化を無効にするコンティニュできます、グループ内に問題が見つかったときに除算問題のファイルを特定できます。)  
  
     使用することができます[/RTC](../../build/reference/rtc-run-time-error-checks.md)デバッグ ビルドでこのようなバグを公開しようとします。  
  
     詳細については、次を参照してください。[コードの最適化](../../build/reference/optimizing-your-code.md)です。  
  
## <a name="see-also"></a>参照  
 [リリース ビルドの問題の解決](../../build/reference/fixing-release-build-problems.md)