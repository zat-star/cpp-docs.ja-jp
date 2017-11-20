---
title: "ライブラリ メンバーの抽出 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Lib
dev_langs: C++
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1c27e5c78316ec48d114bfd1715eb5874772a732
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="extracting-a-library-member"></a>ライブラリ メンバーの抽出
LIB を使用すると、既存のライブラリのメンバーのコピーを格納するオブジェクト (.obj) ファイルを作成します。 メンバーのコピーを抽出するには、次の構文を使用します。  
  
```  
LIB library /EXTRACT:member /OUT:objectfile  
```  
  
 このコマンドの作成と呼ばれる .obj ファイル*objectfile*のコピーを格納する、`member`の*ライブラリ*です。 `member`名は大文字小文字を区別します。 1 つのコマンドで 1 つだけのメンバーを抽出することができます。 /OUT オプションが必要です。既定の出力名はありません。 ファイルが呼び出された場合*objectfile* 、指定したディレクトリに既に存在 (または現在のディレクトリにディレクトリが指定されていない場合*objectfile*)、抽出した*objectfile*既存のファイルを置き換えます。  
  
## <a name="see-also"></a>関連項目  
 [LIB リファレンス](../../build/reference/lib-reference.md)