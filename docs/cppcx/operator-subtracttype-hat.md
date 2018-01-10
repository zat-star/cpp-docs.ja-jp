---
title: "Type 演算子 ^ |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e8d51699d56f1868d5840665017feba2dec50766
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="operator-type"></a>Type^ 演算子
[Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) から `Platform::Type`への変換を有効にします。  
  
## <a name="syntax"></a>構文  
  
```cpp  
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName)  
```  
  
### <a name="return-value"></a>戻り値  
 `Platform::Type` Windows::UI::Xaml::Interop::TypeName [が指定されると、](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx)を返します。  
  
### <a name="remarks"></a>コメント  
 `TypeName` は、型情報を表すための、言語に依存しない Windows ランタイムの構造体です。 [Platform::Type](../cppcx/platform-type-class.md) は C++ に固有で、アプリケーション バイナリ インターフェイス (ABI: Application Binary Interface) を通じて渡すことはできません。 `TypeName`Navigate [関数での](http://msdn.microsoft.com/library/windows/apps/hh702394.aspx) の使用例を次に示します。  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
### <a name="example"></a>例  
 次に、 `TypeName` と `Type`の間の変換方法を示します。  
  
```  
  
// Convert from Type to TypeName  
TypeName tn = TypeName(MainPage::typeid);  
  
// Convert back from TypeName to Type  
Type^ tx2 = (Type^)(tn);  
  
```  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 .NET framework プログラム プロジェクト`TypeName`として[System.Type](assetId:///System.Type?qualifyHint=False&autoUpgrade=True)です。  
  
### <a name="requirements"></a>必要条件  
  
## <a name="see-also"></a>参照  
 [Windows::UI::Xaml::Interop::TypeName 演算子](../cppcx/operator-subtractwindows-ui-xaml-interop-typename.md)   
 [Platform::Type クラス](../cppcx/platform-type-class.md)