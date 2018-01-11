---
title: "コマンド ライン エラー D8016 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D8016
dev_langs: C++
helpviewer_keywords: D8016
ms.assetid: eec51312-7471-4f92-94b2-d517cafc8ef5
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 463de86acf0446f125b66ec1cdc3768c6238b630
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-error-d8016"></a>コマンド ライン エラー D8016
'オプション 1' と '・ オプション 2' のコマンド ライン オプションは互換性がありません。  
  
 コマンド ライン オプションを指定することはできません。  
  
 CL などの環境変数、オプションの指定についてを確認してください。  
  
 **/clr**意味**/EHa**、およびその他の操作を指定することはできません**/EH**コンパイラ オプションを**/clr**です。 詳細については、「[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
 更新した後に d8016 可能性があります、 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 6.0 プロジェクト: プロジェクト更新ウィザードの処理を有効にすることがあります**/RTC**各ソース コードのファイル プロジェクト内には、これよりも優先、 **/RTC**の設定、プロジェクトです。  これを解決するには、変更、 **/RTC**プロジェクト内の各ソース コード ファイルの既定の設定に設定することを意味のプロジェクト設定**/RTC**ファイルごとに有効になります。  
  
 参照してください[/RTC (ランタイム エラー チェック)](../../build/reference/rtc-run-time-error-checks.md)変更する方法について、 **/RTC**プロパティの設定。