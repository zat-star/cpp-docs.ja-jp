---
title: "型およびメンバーの非推奨化 (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# 型およびメンバーの非推奨化 (C++/CX)
C\+\+\/CX では、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型と、プロデューサーおよびコンシューマー用のメンバーに関する非推奨が、[Deprecated](http://msdn.microsoft.com/ja-jp/8b02ad36-3b5f-4361-888b-e6a99040e57c) 属性を使用することでサポートされています。 この属性が適用された API を利用すると、その API は推奨されておらず、代替 API の使用を推奨する警告メッセージがコンパイル時に表示されます。 独自のパブリック型およびメソッドでこの属性を適用し、独自のカスタム メッセージを提供することもできます。  
  
> [!CAUTION]
>  [Deprecated](http://msdn.microsoft.com/ja-jp/8b02ad36-3b5f-4361-888b-e6a99040e57c) 属性は [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型のみで使用することを意図しています。 標準 C\+\+ のクラスおよびメンバーの場合は、[\_\_declspec\(deprecated\)](http://msdn.microsoft.com/library/044swk7y.aspx) を使用します。  
  
## 例  
 次の例では、たとえば Windows ランタイム コンポーネントで、独自のパブリック API を非推奨にする方法を示します。 型 [Windows:Foundation::Metadata::DeprecationType](http://msdn.microsoft.com/ja-jp/ee01e63d-37d0-4273-accc-fca174f88bfa) 型の 2 番目のパラメーターは、API が非推奨であるか、削除済みであるかを指定します。 現在 DeprecationType::Deprecated という値のみがサポートされています。 属性の 3 番目のパラメーターは、属性の適用対象である [Windows::Foundation::Metadata::Platform](http://msdn.microsoft.com/ja-jp/1eae292d-1ab7-4d97-a58c-b0beffd51ef5) を指定します。  
  
```  
  
namespace wfm = Windows::Foundation::Metadata; public ref class Bicycle sealed { public: property double Speed; [wfm::Deprecated("Use the Speed property to compute the angular speed of the wheel", wfm::DeprecationType::Deprecate, 0x0)] double ComputeAngularVelocity(); };  
```  
  
## サポート対象  
 次の表では、Deprecated 属性を適用できるコンストラクトを示します:  
  
||  
|-|  
|XAML コントロール|  
|delegate|  
|event|  
|列挙型フィールド|  
|enum|  
|struct|  
|メソッド|  
|クラス|  
|interface|  
|property|  
|構造体のフィールド|  
|パラメーター化されたコンストラクター|  
  
## 参照  
 [型システム](../cppcx/type-system-c-cx.md)   
 [Visual C\+\+ の言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)