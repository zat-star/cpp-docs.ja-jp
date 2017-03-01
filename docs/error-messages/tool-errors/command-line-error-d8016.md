---
title: "コマンド ライン エラー D8016 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D8016
dev_langs:
- C++
helpviewer_keywords:
- D8016
ms.assetid: eec51312-7471-4f92-94b2-d517cafc8ef5
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 79dad5a5134e91b67a395870e4ff7fa8e14066fb
ms.lasthandoff: 02/24/2017

---
# <a name="command-line-error-d8016"></a>コマンド ライン エラー D8016
'オプション&1;' および 'option2' コマンド ライン オプションは互換性がありません。  
  
 コマンド ライン オプションを同時に指定することはできません。  
  
 CL などの環境変数、オプションの指定を確認してください。  
  
 **/clr**意味**/EHa**、およびその他の操作を指定することはできません**/EH**コンパイラ オプションを**/clr**します。 詳細については、「[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
 更新から D8016 が発生する可能性があります、 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 6.0 プロジェクト: プロジェクト更新ウィザードの処理を有効にすることがあります**/RTC**オーバーライド プロジェクトのソース コード ファイルごとに、 **/RTC**プロジェクトに設定します。  これを解決するには、変更、 **/RTC**プロジェクト設定の既定の設定に、プロジェクト内の各ソース コード ファイルの設定、つまり**/RTC**ファイルごとに有効になります。  
  
 参照してください[/RTC (ランタイム エラー チェック)](../../build/reference/rtc-run-time-error-checks.md)変更する方法について、 **/RTC**プロパティの設定です。
