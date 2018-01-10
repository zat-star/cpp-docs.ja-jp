---
title: ".リンカー入力として exp ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- exporting functions
- import libraries, linker files
- linking [C++], exports
- exporting functions, information about exported functions
- exporting data, export (.exp) files
- functions [C++], exporting
- .exp files [C++]
- EXP files
ms.assetid: 399f5636-0a4d-462e-b500-5f5b9ae5ad22
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5cd6351623b230e3be1e432bd6ee0fb760da5abd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="exp-files-as-linker-input"></a>リンカー入力としての .exp ファイル
エクスポート (.exp) ファイルには、エクスポートされた関数とデータ項目に関する情報が含まれます。 LIB は、インポート ライブラリを作成するときも、.exp ファイルを作成します。 .Exp ファイルを使用するは、両方をエクスポートして直接または間接的に別のプログラムからインポートするプログラムをリンクする場合。 .Exp ファイルとリンクする場合リンクが LIB が既に作成いるいずれかのことを前提としていますので、インポート ライブラリを作成してできません。 .Exp ファイル、およびインポート ライブラリに関する詳細については、「[ライブラリのインポートとエクスポート ファイル](../../build/reference/working-with-import-libraries-and-export-files.md)です。  
  
## <a name="see-also"></a>参照  
 [LINK の入力ファイル](../../build/reference/link-input-files.md)   
 [リンカー オプション](../../build/reference/linker-options.md)