---
title: "Platform::Array クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::Array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Array クラス"
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Platform::Array クラス
アプリケーション バイナリ インターフェイス \(ABI\) を越えて受け渡しでき、変更もできる 1 次元配列を表します。  
  
## 構文  
  
```cpp  
  
template <typename T>  
    private ref class Array<TArg,1> :   
         public WriteOnlyArray<TArg, 1>,  
         public IBoxArray<TArg>  
  
```  
  
## メンバー  
 Platform::Array は [Platform::WriteOnlyArray クラス](../cppcx/platform-writeonlyarray-class.md) からすべてのメソッドを継承し、`Value` の [Platform::IBoxArray インターフェイス](../cppcx/platform-iboxarray-interface.md) プロパティを実装します。  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[Array コンストラクター](../cppcx/array-constructors.md)|クラス テンプレート パラメーター *T* によって指定された型の、変更可能な 1 次元配列を初期化します。|  
  
### メソッド  
 「[Platform::WriteOnlyArray クラス](../cppcx/platform-writeonlyarray-class.md)」を参照してください。  
  
### プロパティ  
  
|||  
|-|-|  
|[Array::Value プロパティ](../cppcx/array-value-property.md)|現在の配列へのハンドルを取得します。|  
  
## 解説  
 この Array クラスはシール クラスであり、継承できません。  
  
 Windows ランタイムの型システムは、ジャグ配列の概念をサポートしていないため、IVector\<Platform::Array\<T\>\> を戻り値またはメソッド パラメーターとして渡すことはできません。 ABI を通じてジャグ配列またはシーケンスのシーケンスを渡すには、`IVector<IVector<T>^>` を使用します。  
  
 Platform::Array を使用するタイミングと方法の詳細については、「[Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)」を参照してください。  
  
 Windows ランタイムの型システムは、ジャグ配列の概念をサポートしていないため、IVector\<Platform::Array\<T\>\> を戻り値またはメソッド パラメーターとして渡すことはできません。 ABI を通じてジャグ配列またはシーケンスのシーケンスを渡すには、`IVector<IVector<T>^>` を使用します。  
  
 このクラスは、コンパイラによって自動的に含まれる vccorlib.h ヘッダーで定義されます。 これは platform.winmd で定義されているパブリック型ではないため、Intellisense では表示されますが、オブジェクト ブラウザーでは表示されません。  
  
## 必要条件  
 コンパイラ オプション: **\/ZW**  
  
## 参照  
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)   
 [Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)