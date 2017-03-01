---
title: "リンカ ツール エラー LNK2005 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2005
dev_langs:
- C++
helpviewer_keywords:
- LNK2005
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
caps.latest.revision: 14
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
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: bf93f364b3dc7156a62eb1c474177eb7b85c7827
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2005"></a>リンカ ツール エラー LNK2005
symbol は既に object で定義されています。  
  
指定された `symbol` (修飾された形式で表示) は重複定義されています。  
  
詳細については、次のサポート技術情報の文書を参照してください。  
  
-   [CRT ライブラリおよび MFC ライブラリが Visual C で間違った順序でリンクされている場合、LNK2005 エラーが発生します。](https://support.microsoft.com/kb/148652)  
  
-   [FIX Global Overloaded Delete Operator 原因 LNK2005](https://support.microsoft.com/kb/140440)  
  
-   [Visual c ATL 実行可能 (.exe) プロジェクトをコンパイルするときに LNK2005 エラーが発生した](https://support.microsoft.com/kb/184235)します。  
  
このエラーは致命的なエラーの後に[LNK1169](../../error-messages/tool-errors/linker-tools-error-lnk1169.md)します。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  使用する場合は、静的および動的なライブラリを混在させる[/clr](../../build/reference/clr-common-language-runtime-compilation.md)します。  
  
2.  シンボルは、パッケージ化された関数 (使用してコンパイルした[/Gy](../../build/reference/gy-enable-function-level-linking.md)) と&1; つ以上のファイルに含まれていますが、コンパイルの間で変更されました。 `symbol` を含むすべてのファイルを再コンパイルします。  
  
3.  symbol は、異なるライブラリの&2; つのメンバー オブジェクトで異なる定義がされており、両方のメンバー オブジェクトが使用されました。  
  
4.  絶対定義が&2; 回行われ、それぞれの定義で値が異なります。  
  
5.  ヘッダー ファイルで変数が宣言および定義されました。 次の解決策が考えられます。  
  
    -   変数を .h で `extern BOOL MyBool;` と宣言し、.c または .cpp ファイルで `BOOL MyBool = FALSE;` と代入します。  
  
    -   変数を宣言して[静的](../../cpp/storage-classes-cpp.md#static)します。  
  
    -   変数を宣言して[selectany](../../cpp/selectany.md)します。  
  
6.  uuid.lib を GUID (oledb.lib や adsiid.lib など) を定義する他の .lib ファイルと組み合わせて使用する場合。 例:  
  
    ```  
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject  
    already defined in uuid.lib(go7.obj)  
    ```  
  
     修正する[/FORCE:MULTIPLE](../../build/reference/force-force-file-output.md)その uuid.lib が最初に参照されるライブラリがリンカーのコマンド ライン オプション、および確認してください。
