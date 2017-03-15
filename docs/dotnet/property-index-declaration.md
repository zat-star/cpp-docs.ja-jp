---
title: "プロパティ インデックスの宣言 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "既定のインデクサー"
  - "既定値, インデクサー"
  - "インデックス付きプロパティ, C++"
  - "インデクサー"
ms.assetid: d898fdbc-2106-4b6a-8c5c-9f511d80fc2f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# プロパティ インデックスの宣言
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

インデックス付きプロパティの宣言の構文は、[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では C\+\+ マネージ拡張から変更されています。  
  
 インデックス付きプロパティに対するマネージ拡張言語サポートには大きな欠点が 2 つあります。1 つは、クラス レベルの添字が使用できないため、すべてのインデックス付きプロパティに対して名前を設定する必要があることです。その結果、`Vector` または `Matrix` クラス オブジェクトに対して直接適用可能な、マネージされた添字演算子などを利用できなくなります。  もう 1 つの欠点は、重要性という点では劣りますが、プロパティとインデックス付きプロパティとを視覚的には判別が困難になることです。パラメーターの数から判別する以外に術がないからです。  最後に、インデックス付きプロパティにはインデックスで指定されていないプロパティと同様の問題があります。つまり、アクセサーが個々のメソッドと別々に定義されており、一体化されていないということです。たとえば、次のようになります。  
  
```  
public __gc class Vector;  
public __gc class Matrix {  
   float mat[,];  
  
public:   
   __property void set_Item( int r, int c, float value);  
   __property float get_Item( int r, int c );  
  
   __property void set_Row( int r, Vector* value );  
   __property Vector* get_Row( int r );  
};  
```  
  
 これを見てわかるように、インデクサーは、2 次元または 1 次元インデックスを示す追加パラメーターによって判別されるだけです。  新しい構文では、インデクサー名の後の角かっこ \(\[、\]\) によってインデクサーの判別が行われます。角かっこ内のパラメーターは、各インデックスの数と型を表しています。  
  
```  
public ref class Vector {};  
public ref class Matrix {  
private:  
   array<float, 2>^ mat;  
  
public:  
   property float Item [int,int] {  
      float get( int r, int c );  
      void set( int r, int c, float value );  
   }  
  
   property Vector^ Row [int] {  
      Vector^ get( int r );  
      void set( int r, Vector^ value );  
   }  
};  
```  
  
 新しい構文を使用して、クラスのオブジェクトに直接適用可能なクラス レベルのインデクサーを指定するには、明示的な名前の代わりに `default` キーワードを再使用します。  たとえば、次のようになります。  
  
```  
public ref class Matrix {  
private:  
   array<float, 2>^ mat;  
  
public:  
   // ok: class level indexer now  
   //  
   //     Matrix mat …  
   //     mat[ 0, 0 ] = 1;   
   //  
   // invokes the set accessor of the default indexer …  
  
   property float default [int,int] {  
      float get( int r, int c );  
      void set( int r, int c, float value );  
   }  
  
   property Vector^ Row [int] {  
      Vector^ get( int r );  
      void set( int r, Vector^ value );  
   }  
};  
```  
  
 新しい構文では、既定のインデックス付きプロパティが指定されると、`get_Item` および `set_Item` という 2 つの名前が予約されます。  これは、既定のインデックス付きプロパティに対して生成される基本名が存在するためです。  
  
 インデックスの場合は、プロパティとは異なり、単純な構文は使用できません。  
  
## 参照  
 [クラスまたはインターフェイス内でのメンバー宣言 \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [方法: インデックス付きプロパティを使用する](../misc/how-to-use-indexed-properties.md)