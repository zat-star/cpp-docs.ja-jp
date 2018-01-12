---
title: "コンテナー (Modern C) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 6e10b758-e928-4827-9c3f-86cafe54bf5b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ffad61c015c38d808b35ebffd98f74733d0997de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="containers-modern-c"></a>コンテナー (Modern C++)  
  
既定では、次のように使用します。[ベクター](../standard-library/vector-class.md) C++ では優先されるシーケンシャルなコンテナーとして。 これに相当`List<T>`.NET 言語でします。  
  
```cpp  
vector<string> apples;  
apples.push_back("Granny Smith");  
```  
  
使用して[マップ](../standard-library/map-class.md)(いない`unordered_map`) 既定の連想コンテナーとして。 使用して[設定](../standard-library/set-class.md)、 [multimap](../standard-library/multimap-class.md)、および[multiset](../standard-library/multiset-class.md)マルチ (&)、逆の場合。  
  
```cpp  
map<string, string> apple_color;  
// ...  
apple_color["Granny Smith"] = "Green";  
```  
  
パフォーマンスの最適化が必要な場合は、次の使用を検討します。  
  
1.  [配列](../standard-library/array-class-stl.md)埋め込みは、クラス メンバーとしてなど、重要なときに入力します。  
  
2.  順序なし [unordered_map] などの連想コンテナー ((../standard-library/unordered-map-class.md)。 これら下の要素ごとのオーバーヘッドありが一定時間の参照が可能正しく効率的に使用するは困難です。  
  
3.  並べ替えられた`vector`です。 詳細については、「[アルゴリズム](../cpp/algorithms-modern-cpp.md)」をご覧ください。  
  
C スタイルの配列を使用しないでください。 データへのアクセスを指示する必要がある従来の api には、アクセサー メソッドをなど使用`f(vec.data(), vec.size());`代わりにします。  
  
コンテナーの詳細については、次を参照してください。 [C++ 標準ライブラリのコンテナー](../standard-library/stl-containers.md)です。  
  
## <a name="see-also"></a>参照  
 [C++ へようこそ](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)
