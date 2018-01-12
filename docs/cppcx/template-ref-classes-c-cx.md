---
title: "テンプレート ref クラス (C + + CX) |Microsoft ドキュメント"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
caps.latest.revision: "15"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b8bb720ef9275f9023cf15986f011573f4c510b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="template-ref-classes-ccx"></a>テンプレート ref クラス (C++/CX)
C++ テンプレートはメタデータに発行されないため、プログラム内でパブリック アクセシビリティおよび保護されたアクセシビリティを持つことはできません。 もちろん、プログラムで、標準 C++ テンプレートを内部的に使用できます。 さらに、パブリック ref クラスをテンプレートとして定義し、明示的に特化したテンプレート ref クラスをプライベート ref クラスのプライベート メンバーとして宣言できます。  
  
## <a name="authoring-ref-class-templates"></a>ref クラス テンプレートの作成  
 次の例は、プライベート ref クラスをテンプレートとして宣言する方法だけでなく、標準 C++ テンプレートを宣言し、それら両方をパブリック ref クラスのメンバーとして宣言する方法も示します。 これで、Windows ランタイム型で、標準 C++ テンプレートを特化できることに注意してください場合、platform::string ^ です。  
  
 [!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]  
  
## <a name="see-also"></a>参照  
 [型システム (C++/CX)](../cppcx/type-system-c-cx.md)   
 [Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)