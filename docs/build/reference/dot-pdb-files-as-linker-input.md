---
title: ".リンカー入力として Pdb ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- .pdb files, as linker input
- PDB files, as linker input
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c5acdc01a58cf0d501be5947cddf710d1b7c6d18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="pdb-files-as-linker-input"></a>リンカー入力としての .pdb ファイル
/Zi オプションを使用してコンパイルされる (.obj) ファイルは、プログラム データベース (PDB) の名前を含むオブジェクトです。 リンカー; に、オブジェクトの PDB ファイル名を指定しません。リンクでは、埋め込み名を使用して、必要な場合は、pdb ファイルを探します。 これはライブラリに含まれるデバッグ可能なオブジェクトにも適用されます。デバッグ可能なライブラリの PDB は、ライブラリと共にリンカーを使用できなければなりません。  
  
 また、リンクは、.exe ファイルまたは .dll ファイルのデバッグ情報を保持するために PDB を使用します。 プログラムの PDB は、出力ファイルと、入力ファイルの両方は、プログラムを再構築時に、リンクが pdb ファイルを更新するためです。  
  
## <a name="see-also"></a>参照  
 [LINK の入力ファイル](../../build/reference/link-input-files.md)   
 [リンカー オプション](../../build/reference/linker-options.md)