---
title: "Type Forwarding (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "type forwarding, Visual C++"
ms.assetid: ae730b69-0c27-41cc-84e1-3132783866ea
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Type Forwarding (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

、アセンブリ A.を使用するクライアントを再コンパイルする必要がないという 1 種類のアセンブリ \(アセンブリ A\) 他の型からアセンブリ \(アセンブリ B\) を移動するには、アセンブリに*転送の* 割り当てをアセンブリのように入力します。  
  
## すべてのプラットフォーム  
 この機能は、すべてのランタイムでサポートされていません。  
  
## Windows ランタイム  
 この機能は [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]ではサポートされていません。  
  
### 要件  
 コンパイラ オプション: **\/ZW**  
  
## 共通言語ランタイム  
 次のコード例は型の転送を使用する方法を示します。  
  
### 構文  
  
```  
#using "new.dll"  
[assembly:TypeForwardedTo(type::typeid)];  
```  
  
### パラメーター  
 `new`  
 、型定義を移動するアセンブリ。  
  
 `type`  
 他のアセンブリに移動先の型定義です。  
  
### 解説  
 コンポーネント \(アセンブリ\) には、クライアント アプリケーションによって他のアセンブリからコンポーネント \(アセンブリ\) から型を移動するために型の転送を使用して用意されて更新コンポーネント \(および必要な追加アセンブリ\) を使用して、後、クライアント アプリケーションは、再コンパイルで機能します。  
  
 既存のアプリケーションが参照するコンポーネントの作業に転送する型。  アプリケーションをビルドし直すと、アプリケーションで使用されるすべての型の適切なアセンブリ参照が必要です。  
  
 型 \(A\)、アセンブリから型を転送する場合、その型の `TypeForwardedTo` 属性、アセンブリ参照を追加する必要があります。  参照先アセンブリには、次のいずれかを使用する必要があります:  
  
-   型 A.の定義。  
  
-   型 A の `TypeForwardedTo` 属性、アセンブリ参照。  
  
 転送できる型の例は次のとおりです。:  
  
-   ref クラス  
  
-   値クラス  
  
-   列挙型  
  
-   インターフェイス  
  
 次の型を転送する:  
  
-   ジェネリック型  
  
-   ネイティブ型  
  
-   入れ子にされた型 \(入れ子にされた型を転送する場合、外側の型を転送する必要があります\)  
  
 共通言語ランタイムに対応するすべての言語で記述されたアセンブリに型を転送できます。  
  
 したがって、アセンブリ A.dll をビルドするために使用したソース ファイルが型定義 \(`ref class MyClass`\) が含まれている場合、そのアセンブリのためにその型定義を移動したいと考え始めました:  
  
1.  B.dll の構築に使用されたソース ファイルに `MyClass` の型定義を移動します。  
  
2.  アセンブリの拡張 DLL をビルドします。  
  
3.  `MyClass` 型の定義を二つの構築に使用するソース・コードから削除し、置換する:  
  
    ```  
    #using "B.dll"  
    [assembly:TypeForwardedTo(MyClass::typeid)];  
    ```  
  
4.  A.dll アセンブリをビルドします。  
  
5.  クライアント アプリケーションの再コンパイルしないで A.dll を使用します。  
  
### 要件  
 コンパイラ オプション: **\/clr**