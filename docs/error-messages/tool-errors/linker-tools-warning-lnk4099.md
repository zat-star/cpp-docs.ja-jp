---
title: "リンカー ツールの警告 LNK4099 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4099
dev_langs:
- C++
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
caps.latest.revision: 9
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
ms.openlocfilehash: 7de3ce64ca3a9c5a5b0738888b6c83b4694bd895
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4099"></a>リンカー ツールの警告 LNK4099
Pdb ファイル 'filename' が見つかりませんでした 'オブジェクト/ライブラリ' または 'path';オブジェクトをリンク デバッグ情報がありません。  
  
 リンカーは、.pdb ファイルを検索できませんでした。 格納されているディレクトリにコピー`object/library`します。  
  
 オブジェクト ファイルに関連付けられている .pdb ファイルの名前を検索するには。  
  
1.  オブジェクト ファイルをライブラリから抽出[lib](../../build/reference/lib-reference.md) **/extract:**`objectname`**.obj** `xyz` **.lib**します。  
  
2.  .Pdb ファイルへのパスを確認して**dumpbin/section:.debug$ T/rawdata** `objectname` **.obj**します。  
  
 コンパイルすることも[/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)pdb ファイルが使用されるか、削除する必要があるため、 [/debug](../../build/reference/debug-generate-debug-info.md)リンカー オプションは、リンク オブジェクトの .pdb ファイルがあるない場合。
