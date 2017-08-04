---
title: "かっこ付きのファイル名を含む | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 5390e52394005b272e928be396e1e23f5edc72d5
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="including-bracketed-filenames"></a>かっこ付きのファイル名を含む
**ANSI 3.8.2** インクルード可能なソース ファイルを見つけるための手段  
  
 山かっこで囲まれたファイル指定の場合、プリプロセッサは親ファイルのディレクトリを検索しません。 "親" ファイルとは、[#include](../preprocessor/hash-include-directive-c-cpp.md) ディレクティブがあるファイルです。 代わりに、コンパイラ コマンド ラインで /I の後に指定したディレクトリからファイル検索を開始します。 /I オプションがない場合または失敗した場合、プリプロセッサは INCLUDE 環境変数を使用して、山かっこで囲まれたインクルード ファイルを検索します。 INCLUDE 環境変数には、セミコロン (**;**) で区切られた複数のパスを含めることができます。 複数のディレクトリが /I オプションの一部として、または INCLUDE 環境変数内にある場合、プリプロセッサではそれらのディレクトリを表示されている順序で検索します。  
  
## <a name="see-also"></a>関連項目  
 [プリプロセス ディレクティブ](../c-language/preprocessing-directives.md)
