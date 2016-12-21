---
title: "threading (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.threading"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "threading attribute"
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# threading (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM オブジェクトに対してスレッド モデルを指定します。  
  
## 構文  
  
```  
  
      [ threading(  
   model=enumeration  
) ]  
```  
  
#### パラメーター  
 ***モデル*** \(省略可能\)  
 次のスレッド モデルの 1 つが :  
  
-   アパートメント スレッド  **アパートメント**  \(\)  
  
-   **依存**  \(ユーザー インターフェイスのない .NET Framework コンポーネント\)  
  
-   **シングル**  \(単純なスレッド\)  
  
-   **フリー \(R\)** \(フリー スレッド\)  
  
-   \( **両方**  とフリー スレッドのアパートメント内\)  
  
 既定値は  **アパートメント**  です。  
  
## 解説  
 **スレッド**  C\+\+ 属性は生成された .idl ファイルには表示されませんがCOM オブジェクトの実装で使用されます。  
  
 ATL プロジェクトでは[コクラス](../windows/coclass.md) の属性がまたはの場合 *モデル*  で指定されたスレッド処理モデルは  **コクラス**  の属性を挿入 [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) クラスのテンプレート パラメーターとして渡されます。  
  
 [ソース](../windows/event-source.md) に **スレッド**  の属性のガードのアクセス。  
  
## 使用例  
 **スレッド**  の使用例については [Licensed](../windows/licensed.md) の例を参照してください。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**  `struct`|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|**コクラス**|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [COM Attributes](../Topic/COM%20Attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [旧形式のコードのためのマルチスレッド サポート \(Visual C\+\+\)](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [Neutral Apartments](http://msdn.microsoft.com/library/windows/desktop/ms681813)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)