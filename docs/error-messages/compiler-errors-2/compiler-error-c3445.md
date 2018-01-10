---
title: "コンパイラ エラー C3445 |Microsoft ドキュメント"
ms.custom: 
ms.date: 04/10/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3445
dev_langs: C++
helpviewer_keywords: C3445
ms.assetid: 0d272bfc-136b-4025-a9ba-5e4eea5f8215
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bf0ba819aa1e8f0a7651e7c42e457b5766c9eefd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3445"></a>コンパイラ エラー C3445
コピーのリストの初期化の '*型*' 明示的なコンス トラクターを使用することはできません  
  
ISO c++ 17 規格に従って、コンパイラはコピーでリストの初期化でオーバー ロードの解決の明示的なコンス トラクターを考慮する必要しますが、そのオーバー ロードが実際選択される場合、エラーが発生する必要があります。  
  
Visual Studio 2017 以降、コンパイラは、Visual Studio 2015 で見つからなかった初期化子リストを使用してオブジェクトの作成に関連するエラーを検索します。 これらのエラーは、クラッシュや未定義の実行時に動作する可能性があります。

## <a name="example"></a>例  
 次の例では、C3445 を生成します。  
  
```cpp  
// C3445.cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    A a1 = { 1 };     // error C3445: copy-list-initialization of 
                      //     'A' cannot use an explicit constructor
}
```  
  
エラーを修正するには、代わりに 直接の初期化を使用します。  
  
```cpp  
// C3445b.cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    A a1{ 1 };
}  
```  
  