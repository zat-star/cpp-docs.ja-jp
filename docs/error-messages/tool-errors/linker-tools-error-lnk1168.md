---
title: "リンカ ツール エラー LNK1168 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1168
dev_langs: C++
helpviewer_keywords: LNK1168
ms.assetid: 97ead151-fd99-46fe-9a1d-7e84dc0b8cc8
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12dfce4243f0872735158df7ccd81b7c6e29efc8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1168"></a>リンカ ツール エラー LNK1168
書き込みモードで 'filename' を開けません。  
  
 リンカーは `filename` に書き込むことができません。 ファイルが使用中で、そのファイル ハンドルが別のプロセスによってロックされている可能性があります。または、ファイルに対する書き込みアクセス許可、あるいはファイルが配置されているディレクトリやネットワーク共有に対する書き込みアクセス許可がない可能性があります。 このエラーの原因は、多くの場合、ウイルス対策プログラムによって設定されているロック、ファイル検索インデックス作成プロセス、[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] ビルド システムが設定したロックを解除する際に発生する遅延のように一時的なものです。  
  
 この問題を解決するには、`filename` ファイル ハンドルがロックされていないこと、およびファイルに対する書き込みアクセス許可があることを確認します。 実行可能ファイルの場合は、そのファイルが実行されていないことを確認します。  
  
 Windows SysInternals ユーティリティを使用して[処理](http://technet.microsoft.com/sysinternals/bb896655.aspx)または[プロセス エクスプ ローラー](http://technet.microsoft.com/sysinternals/bb896653)ファイルのハンドルのロックを保持しているプロセスを決定する`filename`です。 また、プロセス エクスプローラーを使用して、開いているファイル ハンドルのロックを解除することもできます。 これらのユーティリティの使用方法については、そのユーティリティに付属のヘルプ ファイルを参照してください。  
  
 ファイルがウイルス対策プログラムによってロックされている場合、この問題を解決するには、ウイルス対策プログラムによる自動スキャンの対象からビルド出力ディレクトリを除外します。 ウイルス対策スキャナーは、多くの場合、ファイル システムで新しいファイルを作成することにより実行され、スキャンの実行中は、このスキャナーによりファイルがロックされます。 特定のディレクトリをスキャン対象から除外する方法の詳細については、ウイルス対策プログラムのドキュメントを参照してください。  
  
 ファイルが検索インデックス作成サービスによってロックされている場合、この問題を解決するには、自動インデックス作成の対象からビルド出力ディレクトリを除外します。 詳細については、インデックス作成サービスのドキュメントを参照してください。 Windows 検索インデックス作成サービスを変更するには、使用**インデックスのオプション**windows**コントロール パネルの** です。 詳細については、次を参照してください。 [Windows の検索インデックスを使用する: よく寄せられる質問](http://windows.microsoft.com/en-us/windows/improve-windows-searches-using-index-faq#1TC=windows-7)です。  
  
 ビルド処理で実行可能ファイルを上書きできない場合、そのファイルは、ファイル エクスプローラーによってロックされている可能性があります。 場合、**アプリケーション エクスペリエンス**サービスが無効で、ファイル エクスプ ローラーのすることは、実行可能ファイル ハンドルのロックを一定の時間。 この問題を解決するには実行**services.msc**を開き、**プロパティ**のダイアログ ボックス、**アプリケーション エクスペリエンス**サービス。 変更、**スタートアップの種類**から**無効になっている**に**手動**です。  
  
## <a name="see-also"></a>参照  
 [ソリューションまたは Visual C で ActiveX プロジェクトをビルドしようとしたときに"error PRJ0008"または"Fatal error LNK1168"のエラー メッセージを受信する可能性があります。](http://support.microsoft.com/kb/308358)