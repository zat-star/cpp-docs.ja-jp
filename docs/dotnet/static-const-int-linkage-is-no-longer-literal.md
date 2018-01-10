---
title: "Static Const Int リンケージの非リテラル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- literal attribute [C++]
- constants, declaring
- integral constant expressions
ms.assetid: d2a5e3d2-ffb0-4b61-8114-bec5993a1195
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8f34682fa780ef430d27104d3df9658f9e32ad39
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="static-const-int-linkage-is-no-longer-literal"></a>静的整数型定数リンケージの非リテラル化
定数、クラスのメンバーの宣言は、Visual C を c++ マネージ拡張から変更されました。  
  
 `static const`整数メンバーはサポートされても、そのリンケージ属性が変更されました。 以前のリンケージ属性は、リテラルの整数メンバーで今すぐ実行されます。 たとえば、次のマネージ拡張クラスがあるとします。  
  
```  
public __gc class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 これには、(リテラルの属性に注意してください) のフィールドに対して、次の基になる CIL 属性が生成されます。  
  
```  
.field public static literal int32   
modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 これは、新しい構文で引き続きコンパイル: 中  
  
```  
public ref class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 不要になったリテラルの属性を出力し、したがってとは見なされません、定数、CLR ランタイムによって。  
  
```  
.field public static int32 modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 同じ間言語 literal 属性がある、するためには、宣言を変更する必要が新たにサポートする`literal`、次のように、データ メンバー  
  
```  
public ref class Constants {  
public:  
   literal int LOG_DEBUG = 4;  
};  
```  
  
## <a name="see-also"></a>参照  
 [クラスまたはインターフェイス内でメンバーの宣言 (C + + CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [リテラル](../windows/literal-cpp-component-extensions.md)