---
title: "リンカー ツールの警告 LNK4099 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4099
dev_langs: C++
helpviewer_keywords: LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 364c2f9303707328ebf3bdf3284398e6d4f9f0d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4099"></a>リンカー ツールの警告 LNK4099
Pdb ファイル 'filename' が見つかりませんでした 'オブジェクト/ライブラリ' または 'path';オブジェクトをリンク デバッグ情報がありません。  
  
 リンカーは、.pdb ファイルが見つかりませんでした。 格納されているディレクトリにコピー`object/library`です。  
  
 オブジェクト ファイルに関連付けられている .pdb ファイルの名前が見つかりません。  
  
1.  オブジェクト ファイルをライブラリから抽出[lib](../../build/reference/lib-reference.md) **抽出/:**`objectname`**.obj** `xyz` **.lib**です。  
  
2.  .Pdb ファイルへのパスを確認して**dumpbin/section:.debug$ T/rawdata** `objectname` **.obj**です。  
  
 コンパイルすることも[/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)pdb を使用する、または削除する必要はありませんので、 [/debug](../../build/reference/debug-generate-debug-info.md)リンカー オプションは、リンク オブジェクトの .pdb ファイルがあるない場合。