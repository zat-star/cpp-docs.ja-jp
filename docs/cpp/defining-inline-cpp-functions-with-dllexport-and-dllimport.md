---
title: "Dllexport と dllimport を使用したインライン C++ 関数の定義 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- inline functions [C++], defining
- functions [C++], defining inline
- dllimport attribute [C++], inline functions
- dllexport attribute [C++], inline functions
ms.assetid: 3b48678b-e7b8-4eda-bb46-b5d34dcf7817
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: de62d695a1f2553a701fde86af2238a499aebd48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="defining-inline-c-functions-with-dllexport-and-dllimport"></a>dllexport と dllimport を使用したインライン C++ 関数の定義
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 `dllexport` 属性を使用すると、関数をインラインとして定義できます。 この場合、関数は、プログラムのモジュールがその関数を参照しているかどうかにかかわらず、常にインスタンス化され、エクスポートされます。 関数は、他のプログラムによってインポートされることを前提としています。  
  
 また、**dllimport** 属性付きで宣言された関数をインラインで定義することもできます。 この場合、関数は、(/Ob の指定に応じて) 展開はできても、インスタンス化はできません。 特に、インラインでインポートされた関数のアドレスが使用される場合、DLL 内の関数のアドレスが返されます。 この動作は、インポートされた非インライン関数のアドレスを受け取ることと同じです。  
  
 これらの規則は、クラス定義内に定義が出現するインライン関数に適用されます。 また、インライン関数の静的なローカル データと文字列は、単一のプログラム (つまり、DLL インターフェイスのない実行可能ファイル) 内に存在している場合のように、同じ ID を DLL とクライアント間で保持します。  
  
 インポートされたインライン関数を用意する場合は注意が必要です。 たとえば、DLL を更新する場合は、クライアントが変更されたバージョンの DLL を使用すると仮定しないでください。 適切なバージョンの DLL が読み込まれるように、DLL のクライアントもリビルドしてください。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [dllexport、dllimport](../cpp/dllexport-dllimport.md)