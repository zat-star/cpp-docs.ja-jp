---
title: "テンプレート ref クラス (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
caps.latest.revision: 15
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 15
---
# テンプレート ref クラス (C++/CX)
C\+\+ テンプレートはメタデータに発行されないため、プログラム内でパブリック アクセシビリティおよび保護されたアクセシビリティを持つことはできません。 もちろん、プログラムで、標準 C\+\+ テンプレートを内部的に使用できます。 さらに、パブリック ref クラスをテンプレートとして定義し、明示的に特化したテンプレート ref クラスをプライベート ref クラスのプライベート メンバーとして宣言できます。  
  
## ref クラス テンプレートの作成  
 次の例は、プライベート ref クラスをテンプレートとして宣言する方法だけでなく、標準 C\+\+ テンプレートを宣言し、それら両方をパブリック ref クラスのメンバーとして宣言する方法も示します。[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型 \(この場合は Platform::String^\) を使用して、標準 C\+\+ テンプレートを特化できることに注意してください。  
  
 [!code-cpp[cx_templates#01](../snippets/cpp/VS_Snippets_Misc/cx_templates/cpp/class1.h#01)]  
  
## 参照  
 [型システム \(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)   
 [Visual C\+\+ の言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)