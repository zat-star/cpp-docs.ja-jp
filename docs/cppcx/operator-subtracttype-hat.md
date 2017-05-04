---
title: "Type^ 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Type^ 演算子
[Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) から `Platform::Type` への変換を有効にします。  
  
## 構文  
  
```cpp  
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName)  
```  
  
## 戻り値  
 [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) が指定されると、`Platform::Type` を返します。  
  
## 解説  
 `TypeName` は、型情報を表すための、言語に依存しない Windows ランタイムの構造体です。[Platform::Type](../cppcx/platform-type-class.md) は C\+\+ に固有で、アプリケーション バイナリ インターフェイス \(ABI: Application Binary Interface\) を通じて渡すことはできません。[Navigate](http://msdn.microsoft.com/library/windows/apps/hh702394.aspx) 関数での `TypeName` の使用例を次に示します。  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
## 使用例  
 次に、`TypeName` と `Type` の間の変換方法を示します。  
  
```  
  
// Convert from Type to TypeName TypeName tn = TypeName(MainPage::typeid); // Convert back from TypeName to Type Type^ tx2 = (Type^)(tn);  
  
```  
  
## 同等の .NET Framework 関数  
 `TypeName` に相当する .NET Framework プログラム プロジェクト [System.Type](assetId:///System.Type?qualifyHint=False&amp;autoUpgrade=True)。  
  
## 必要条件  
  
## 参照  
 [Windows::UI::Xaml::Interop::TypeName 演算子](../cppcx/operator-subtractwindows-ui-xaml-interop-typename.md)   
 [Platform::Type クラス](../cppcx/platform-type-class.md)