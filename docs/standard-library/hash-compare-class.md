---
title: "hash_compare クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "hash_set/stdext::hash_compare"
  - "std.hash_compare"
  - "hash_compare"
  - "std::hash_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_compare クラス"
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# hash_compare クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テンプレート クラスは、任意のハッシュ連想コンテナー — hash\_map、hash\_multimap、hash\_set、または hash\_multiset — によって使用可能なオブジェクトを示しています。既定では **Traits** パラメーター オブジェクトを使用して、含まれる要素の順序付けおよびハッシュを行います。  
  
## 構文  
  
```  
template<class Key, class Traits = less<Key> >  
   class hash_compare  
   {  
   Traits comp;  
public:  
   const size_t bucket_size = 4;  
   const size_t min_buckets = 8;  
   hash_compare( );  
   hash_compare( Traits pred );  
   size_t operator( )( const Key& _Key ) const;  
   bool operator( )(   
      const Key& _Key1,  
      const Key& _Key2  
   ) const;  
   };  
```  
  
## 解説  
 各ハッシュ連想コンテナーは、**Traits** 型のハッシュ特性 オブジェクト \(テンプレート パラメーター\) を格納します。  特定の関数とオブジェクトを選択的に無視するために hash\_compare を特殊化してクラスを派生させるか、特定の最小要件を満たしているこのクラスの独自のバージョンを使用することができます。  具体的には、**hash\_compare\<Key, Traits\>** 型のオブジェクト hash\_comp について、上記のコンテナーで次の動作が必要です。  
  
-   **Key** 型のすべての値 `_Key` について、呼び出し **hash\_comp**\(`_Key`\) はハッシュ関数として機能し、**size\_t** 型の値の分布を生成します。  hash\_compare によって提供される関数は `_Key` を返します。  
  
-   並べ替え順序において `_Key2` の前になる、同じハッシュ値 \(ハッシュ関数によって返される値\) を持つ **Key** 型の任意の値 `_Key1` について、**hash\_comp**\(`_Key2`、`_Key1`\) は false になります。  関数は、**Key** 型の値の完全な順序付けを強制する必要があります。  hash\_compare によって提供される関数は *comp*\(`_Key2`、`_Key1`\)`,` を返します。ここで、*comp* は **Traits** 型の格納されているオブジェクトを示し、オブジェクト hash\_comp を構築する際に指定できます。  既定の **Traits** パラメーター型 **less\<Key\>** について、並べ替えキーの値が減少することはありません。  
  
-   整数の定数 **bucket\_size** は、コンテナーが超えるべきでない、「バケット」\(ハッシュ テーブルのエントリ\) ごとの要素の平均数を指定します。  0 より大きくなければなりません。  hash\_compare によって提供される値は 4 です。  
  
-   整数の定数 **min\_buckets** は、ハッシュ テーブルに保持するバケットの最小数を指定します。  2 の累乗で、0 より大きくなければなりません。  hash\_compare によって提供される値は 8 です。  
  
 Visual C\+\+ .NET 2003 では、[\<hash\_map\>](../standard-library/hash-map.md) ヘッダー ファイルと [\<hash\_set\>](../standard-library/hash-set.md) ヘッダー ファイルのメンバーは、std 名前空間に存在しなくなりましたが、stdext 名前空間に移動されました。  詳細については、「[The stdext Namespace](../Topic/stdext%20Namespace.md)」を参照してください。  
  
## 使用例  
 hash\_compare の宣言方法や使用方法の例については、[hash\_map::hash\_map](../Topic/hash_map::hash_map.md)、[hash\_multimap::hash\_multimap](../Topic/hash_multimap::hash_multimap.md), [hash\_set::hash\_set](../Topic/hash_set::hash_set.md)、および [hash\_multiset::hash\_multiset](../Topic/hash_multiset::hash_multiset.md) の例を参照してください。  
  
## 必要条件  
 **ヘッダー:** \<hash\_map\>  
  
 **名前空間:** stdext  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)