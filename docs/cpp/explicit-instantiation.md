---
title: "明示的なインスタンス化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- templates, instantiation
- explicit instantiation
- instantiation, explicit
ms.assetid: 8b0d4e32-45a6-49d5-8041-1ebdd674410e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e272652ecc82b65d0251194f17a746ddde58fcc1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="explicit-instantiation"></a>明示的なインスタンス化
明示的なインスタンス化によって、テンプレート化されたクラスまたは関数をコードで実際に使用することなく、そのインスタンスを作成できます。 配布用のテンプレートを使用するライブラリ (.lib) ファイルを作成する場合は、この方法が便利です。そのため、インスタンス化されないテンプレート定義はオブジェクト (.obj) ファイルに格納されません。  
  
 次のコードは `MyStack` 変数と 6 つの項目に対して明示的に `int` をインスタンス化します。  
  
```cpp  
template class MyStack<int, 6>;  
```  
  
 このステートメントは、オブジェクトのためのストレージを予約しないで `MyStack` のインスタンス化を作成します。 コードはすべてのメンバーに対して生成されます。  
  
 次の行はコンストラクター メンバー関数のみを明示的にインスタンス化します。  
  
```cpp  
template MyStack<int, 6>::MyStack( void );  
```  
  
 明示的にインスタンス化関数テンプレートを使用して、特定の型引数をそれらを再宣言の例で示すように[関数テンプレートのインスタンス化](../cpp/function-template-instantiation.md)です。  
  
 `extern` キーワードを使用して、メンバーが自動的にインスタンス化されないようにすることができます。 例:  
  
```cpp  
extern template class MyStack<int, 6>;  
```  
  
 同様に、外部のインスタンス化されていないメンバーとして特定のメンバーを次のようにマークできます。  
  
```cpp  
extern template MyStack<int, 6>::MyStack( void );  
```  
  
 `extern` キーワードを使用して、コンパイル時、複数のオブジェクト モジュールで同じコードがインスタンスされないようにできます。 関数が呼び出される場合には、少なくとも 1 つのリンクされたモジュールで指定した明示的なテンプレート パラメーターを使用して、テンプレート関数をインスタンス化する必要があります。そのようにインスタンス化しないと、プログラムのビルド時にリンカー エラーが発生します。  
  
> [!NOTE]
>  特殊化の `extern` キーワードは、クラス本体の外部で定義されたメンバー関数にのみ適用されます。 クラス宣言内で定義されている関数はインライン関数と見なされ、常にインスタンス化されます。  
  
## <a name="see-also"></a>参照  
 [関数テンプレート](../cpp/function-templates.md)