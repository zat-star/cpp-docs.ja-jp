---
title: "リンカ ツール エラー LNK2011 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2011
dev_langs: C++
helpviewer_keywords: LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a660356f719003a06c17d1fddba948e9d903e00a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2011"></a>リンカ ツール エラー LNK2011
プリコンパイル済みのオブジェクトがリンクされていません。イメージは動作しない可能性があります。  
  
 プリコンパイル済みヘッダーを使用する場合は、すべてのプリコンパイル済みヘッダーで作成されたオブジェクト ファイルはでリンクされているリンクが必要です。 使用する他のソース ファイルで使用するためのプリコンパイル済みヘッダーを生成するソース ファイルがあれば、オブジェクト ファイルも含める必要があります。  
  
 使用するためのプリコンパイル済みヘッダー ファイルを作成するその他のソース STUB.cpp という名前のファイルをコンパイルする場合 stub.obj も一緒にリンクする必要がありますなど、このエラーが表示されます。 次のコマンドラインはいずれかの線を使用して、COMMON.pch PROG1.cpp と PROG2.cpp 2 および 3 の行で使用されている、プリコンパイル済みヘッダーを作成します。 STUB.cpp だけを含んだファイル`#include`行 (同じ`#include`PROG1.cpp、PROG2.cpp 行) と、プリコンパイル済みヘッダーの生成にのみ使用されます。 最後の行で、LNK2011 を回避する stub.obj も一緒にリンクされます必要があります。  
  
```  
cl /c /Yccommon.h stub.cpp  
cl /c /Yucommon.h prog1.cpp  
cl /c /Yucommon.h prog2.cpp  
link /out:prog.exe stub.obj prog1.obj prog2.obj  
```