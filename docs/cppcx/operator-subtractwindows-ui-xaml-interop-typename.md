---
title: "Windows::UI::Xaml::Interop::TypeName 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Windows::UI::Xaml::Interop::TypeName 演算子
`Platform::Type` から [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) 変換できるようになります。  
  
## 構文  
  
```cpp  
Operator TypeName(Platform::Type^ type)  
```  
  
## 戻り値  
 `Platform::Type^` が指定されていると、[Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) が返されます。  
  
## 解説  
 `TypeName` は、型情報を表すための、言語に依存しない Windows ランタイムの構造体です。[Platform::Type](../cppcx/platform-type-class.md) は C\+\+ に固有で、アプリケーション バイナリ インターフェイス \(ABI: Application Binary Interface\) を通じて渡すことはできません。[Navigate](http://msdn.microsoft.com/library/windows/apps/hh702394.aspx) 関数での `TypeName` の使用例を次に示します。  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
## 使用例  
 次に、`TypeName` と `Type` の間の変換方法を示します。  
  
```  
  
// Convert from Type to TypeName Windows::UI::Xaml::Interop::TypeName tn = TypeName(MainPage::typeid); // Convert back from TypeName to Type Type^ tx2 = (Type^)(tn);  
  
```  
  
## 同等の .NET Framework 関数  
 `TypeName` に相当する .NET Framework プログラム プロジェクト [System.Type](assetId:///System.Type?qualifyHint=False&amp;autoUpgrade=True)。  
  
## 必要条件  
  
## 参照  
 [operator Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-subtractwindows-ui-xaml-interop-typename.md)   
 [Platform::Type クラス](../cppcx/platform-type-class.md)