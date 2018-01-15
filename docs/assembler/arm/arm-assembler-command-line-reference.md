---
title: "ARM アセンブラーのコマンド ライン リファレンス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: f7b89478-1ab5-4995-8cde-a805f0462c45
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5e7f69c2ac2dbd8a0079d9160100077ccd35513e
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="arm-assembler-command-line-reference"></a>ARM アセンブラーのコマンド ライン リファレンス
この記事は、Microsoft ARM アセンブラーに関するコマンド ラインの情報を提供*armasm*、Microsoft による実装のオブジェクト ファイル形式 COFF (Common) に常に ARMv7 Thumb アセンブリ言語をコンパイルします。 リンカーは、COFF コードと ARM アセンブラーによって、またはオブジェクト ライブラリ、ライブラリアンによって作成されると共に、C コンパイラによって生成されるオブジェクト コードをリンクできます。  
  
## <a name="syntax"></a>構文  
  
```  
armasm [[options]] sourcefile objectfile  
```  
  
```  
armasm [[options]] -o objectfile sourcefile  
```  
  
#### <a name="parameters"></a>パラメーター  
 `options`  
 -エラー`filename`  
 エラーと警告メッセージをリダイレクト`filename`です。  
  
 は`dir[;dir]`  
 インクルード検索パスに指定されたディレクトリを追加します。  
  
 -事前に定義`directive`  
 定義済みのシンボルを備える、SETL、セット、またはディレクティブを指定します。 例: **armasm.exe-「備える 150 のカウント」source.asm を事前に定義**です。詳細については、次を参照してください。、 [ARM アセンブラー ツール ガイド](http://go.microsoft.com/fwlink/p/?linkid=246102)です。  
  
 -nowarn  
 すべての警告メッセージを無効にします。  
  
 -無視します。`warning`  
 指定された警告を無効にします。 使用可能な値は、警告に関するセクションを参照してください。  
  
 -ヘルプ  
 コマンド ライン ヘルプ メッセージを印刷します。  
  
 -コンピューター`machine`  
 PE ヘッダーに設定するコンピューターの種類を指定します。  指定できる値`machine`は。  
**ARM**— IMAGE_FILE_MACHINE_ARMNT にコンピューターの種類を設定します。 既定値です。   
**THUMB**— IMAGE_FILE_MACHINE_THUMB にコンピューターの種類を設定します。  
  
 -oldit  
 常に ARMv7 スタイルを生成する IT ブロックします。  既定では、ARMv8 と互換性のある IT ブロックが生成されます。  
  
 -経由で`filename`  
 追加のコマンドライン引数を読み取る`filename`です。  
  
 -16  
 16 ビット Thumb 命令としてソースを編成します。  既定値です。  
  
 -32  
 32 ビット ARM 命令としてソースを編成します。  
  
 -g  
 デバッグ情報を生成します。  
  
 -errorreport:`option`  
 Microsoft にエラーがどのように内部アセンブラーを指定します。  指定できる値`option`は。   
**none**— レポートを送信しません。   
**プロンプト**— レポートをすぐに送信するように求めます。   
**キュー**: 次の管理者ログオンでレポートを送信するように求めます。 既定値です。   
**送信**— レポートを自動的に送信します。  
  
 `sourcefile`  
 ソース ファイルの名前です。  
  
 `objectfile`  
 オブジェクト (出力) ファイルの名前。  
  
 次の例では、一般的なシナリオで armasm を使用する方法を示します。 まず、armasm を使用して、オブジェクト (.obj) ファイルへのアセンブリ言語のソース (.asm) ファイルをビルドします。 CL のコマンド ライン C コンパイラを使用して、ソース (.c) ファイルをコンパイルし、ARM オブジェクト ファイルをリンクするリンカー オプションも指定します。  
  
 **armasm myasmcode.asm-o myasmcode.obj**  
  
 **cl myccode.c/link myasmcode.obj**  
  
## <a name="see-also"></a>参照  
 [ARM アセンブラー診断メッセージ](../../assembler/arm/arm-assembler-diagnostic-messages.md)   
 [ARM アセンブラー ディレクティブ](../../assembler/arm/arm-assembler-directives.md)