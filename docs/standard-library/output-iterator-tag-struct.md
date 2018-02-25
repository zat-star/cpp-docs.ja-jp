---
title: "output_iterator_tag 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xutility/std::output_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- output_iterator_tag class
- output_iterator_tag struct
ms.assetid: c23a4331-b069-4fa0-9c3a-1c9be7095553
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d974e9f9e1b53a6595d8a75e75d6e9bb15dba230
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="outputiteratortag-struct"></a>output_iterator_tag 構造体
出力反復子を表す **iterator_category** 関数の戻り値の型を提供するクラス。  
  
## <a name="syntax"></a>構文  
  
struct output_iterator_tag {};  
  
## <a name="remarks"></a>コメント  
 カテゴリ タグ クラスはアルゴリズムの選択にコンパイル タグとして使用されます。 テンプレート関数は、コンパイル時に最も効率的なアルゴリズムを利用できるように、その反復子引数の最も具体的なカテゴリを見つける必要があります。 `Iterator` 型の反復子ごとに、反復子の動作を表す最も具体的なカテゴリ タグとして `iterator_traits`< `Iterator`> **::iterator_category** を定義する必要があります。  
  
 この型は、**Iter** が出力反復子としてサービスを提供するオブジェクトを表すとき、**iterator**\< **Iter**> **::iterator_category** と同じになります。  
  
 このタグは、出力反復子には `value_type` または `difference_type` がないため、他の反復子タグと同様、反復子の `value_type` または `difference_type` でパラメーター化されません。  
  
## <a name="example"></a>例  
 **iterator_tag** の使用例については、「[iterator_traits](../standard-library/iterator-traits-struct.md)」または「[random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<iterator>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)



