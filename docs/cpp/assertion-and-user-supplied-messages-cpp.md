---
title: "アサーションとユーザー指定のメッセージ (C++) |Microsoft ドキュメント"
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
- user-supplied messages [C++], run time
- user-supplied messages [C++], preprocessor time
- '#error%2C assert%2C static_assert [C++]'
- user-supplied messages [C++], compile time
ms.assetid: ebf7d885-61c8-4233-b0ae-1c9a38e0f385
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: def12cc22267d2cc25be790b7e6e6eebd4c46479
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="assertion-and-user-supplied-messages-c"></a>アサーションとユーザー指定のメッセージ (C++)
C++ 言語サポートする 3 つエラー処理メカニズムするのに役立つアプリケーションのデバッグ: [#error ディレクティブ](../preprocessor/hash-error-directive-c-cpp.md)、 [static_assert](../cpp/static-assert.md)キーワード、および[assert マクロ、_assert、_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)マクロです。 3 つの機構すべてはエラー メッセージを発行し、2 つはソフトウェアのアサーションもテストします。 ソフトウェアのアサーションは、プログラムの特定位置にある true となるはずの条件を指定します。 コンパイル時にアサーションが失敗した場合、コンパイラで診断メッセージが発行され、コンパイル エラーが発生します。 ランタイムのアサーションが失敗した場合、オペレーティング システムで診断メッセージが発行され、アプリケーションを終了します。  
  
## <a name="remarks"></a>コメント  
 アプリケーションの有効期間は、プリプロセス、コンパイル、および実行時フェーズで構成されます。 各エラー処理機構は、これらのいずれかのフェーズで使用できるデバッグ情報にアクセスします。 効果的にデバッグするには、そのフェーズに関する適切な情報を提供する機能を選択します:  
  
-   [#Error ディレクティブ](../preprocessor/hash-error-directive-c-cpp.md)プリプロセス時に有効になっています。 これは無条件にユーザー指定のメッセージを出力し、コンパイルはエラーで失敗します。 メッセージは、プリプロセッサ ディレクティブが操作するテキストを含むことができますが、結果の式は評価されません。  
  
-   [Static_assert](../cpp/static-assert.md)宣言はコンパイル時に有効にします。 これはブール型に変換できるユーザー指定の整数式で表されるソフトウェアのアサーションをテストします。 式がゼロ (false) に評価されると、ユーザー指定のメッセージが表示され、コンパイルはエラーで失敗します。  
  
     `static_assert` の宣言は、テンプレート引数をユーザー指定の式に含めることができるため、テンプレートをデバッグする場合に特に便利です。  
  
-   [Assert マクロ、_assert、_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)マクロは実行時に有効にします。 ユーザーが指定した式が評価され、結果がゼロの場合、システムは診断メッセージを発行し、アプリケーションを閉じます。 その他の多くのマクロなど[_ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)と`_ASSERTE`には、このマクロに似ていますが、別のシステム定義またはユーザー定義の診断メッセージを発行します。  
  
## <a name="see-also"></a>関連項目  
 [#error ディレクティブ (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)   
 [assert マクロ、_assert、_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [_ASSERT、_ASSERTE、_ASSERT_EXPR マクロ](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)   
 [static_assert](../cpp/static-assert.md)   
 [_STATIC_ASSERT マクロ](../c-runtime-library/reference/static-assert-macro.md)   
 [テンプレート](../cpp/templates-cpp.md)
