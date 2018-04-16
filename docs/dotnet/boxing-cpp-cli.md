---
title: "ボックス化 (C + + CLI) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: f4ee27a8-6a34-432d-b9ec-39285d513b23
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e49c6f82099e6d7dbcfc47079d19228d7a91dc05
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="boxing-ccli"></a>ボックス化 (C++/CLI)
値の型を型に変換するプロセスはボックス化が`object`または値の型によって実装されるインターフェイスの種類。 値型がボックス化、共通言語ランタイム (CLR) の値を折り返した、`System.Object`され、マネージ ヒープに格納します。 ボックス化解除すると、値型がオブジェクトから抽出されます。 ボックス化は暗黙的に行われ、ボックス化解除すると明示的になります。  
  
## <a name="related-articles"></a>関連トピック  
  
|タイトル|説明|  
|-----------|-----------------|  
|[方法: 明示的にボックス化を要求する](../dotnet/how-to-explicitly-request-boxing.md)|変数をボックス化を明示的に要求する方法について説明します。|  
|[方法: gcnew を使用して値型を作成し、暗黙的なボックス化を使用する](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)|使用する方法を示します`gcnew`管理、ガベージ コレクトされたヒープに配置可能なボックス化された値の種類を作成します。|  
|[方法: ボックス化を解除する](../dotnet/how-to-unbox.md)|ボックス化を解除し、値を変更する方法を示します。|  
|[標準変換と暗黙のボックス化](../dotnet/standard-conversions-and-implicit-boxing.md)|ボックス化を必要とする変換をコンパイラによって、標準変換が選択されていることを示します。|  
|[C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|Visual C のドキュメントでの .NET プログラミングのトップレベルの記事です。|