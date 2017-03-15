---
title: "ボックス化 (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: f4ee27a8-6a34-432d-b9ec-39285d513b23
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ボックス化 (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ボックス化とは、値型 `object` または値型によって実装されるインターフェイス型へ変換するプロセスです。  Common Language Runtime \(CLR\) は、値型がボックス化されるとき、`System.Object` および格納の値をマネージ ヒープにラップします。  ボックス化解除すると、値型がオブジェクトから抽出されます。  ボックス化は暗黙的であり、ボックス化解除すると明示的になります。  
  
## 関連トピック  
  
|タイトル|説明|  
|----------|--------|  
|[方法: 明示的にボックス化を要求する](../Topic/How%20to:%20Explicitly%20Request%20Boxing.md)|明示的に変数のボックス化を要求する方法について説明します。|  
|[方法: gcnew を使用して値型を作成し、暗黙的なボックス化を使用する](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)|`gcnew` をマネージ コードに配置できるボックス化された値型ガベージ コレクトされたヒープを作成する方法を示します。|  
|[方法: ボックス化を解除する](../dotnet/how-to-unbox.md)|ボックス化解除出力値を変更する方法を示します。|  
|[標準変換と暗黙のボックス化](../dotnet/standard-conversions-and-implicit-boxing.md)|標準変換はボックス化を必要とする変換に対してコンパイラで選択されていることを示します。|  
|[C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|Visual C\+\+ のドキュメントでの .NET プログラミングのトップレベル論文。|