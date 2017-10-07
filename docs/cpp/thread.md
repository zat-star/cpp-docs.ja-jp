---
title: "スレッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- thread_cpp
dev_langs:
- C++
helpviewer_keywords:
- thread local storage (TLS)
- thread __declspec keyword
- TLS (thread local storage), compiler implementation
- __declspec keyword [C++], thread
ms.assetid: 667f2a77-6d1f-4b41-bee8-05e67324fab8
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: f460497071445cff87308fa9bf6e0d43c6f13a3e
ms.openlocfilehash: 7261dc1d6d76eeac8a6b2959bc9bb6fc3c98a66e
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="thread"></a>スレッド

**Microsoft 固有の仕様**  
**スレッド**拡張ストレージ クラス修飾子を使用して、スレッド ローカル変数を宣言します。 移植可能な c++ 11 では同等で、後で、使用、 [thread_local](../cpp/storage-classes-cpp.md#thread_local)ストレージ クラス指定子。

## <a name="syntax"></a>構文

```
__declspec( thread ) declarator
```

## <a name="remarks"></a>コメント

スレッド ローカル ストレージ (TLS) は、特定のマルチスレッド プロセスの各スレッドが、スレッド固有のデータを格納するための場所を割り当てる機能です。 標準のマルチスレッド プログラムでは、データは特定のプロセスのすべてのスレッド間で共有されますが、スレッド ローカル ストレージはスレッドごとのデータを割り当てるための機能です。 スレッドの詳細については、次を参照してください。[マルチ スレッド](../parallel/multithreading-support-for-older-code-visual-cpp.md)です。

スレッド ローカル変数の宣言を使用する必要があります[拡張属性構文](../cpp/declspec.md)と`__declspec`キーワード、**スレッド**キーワード。 たとえば、次に示すコードは、整数型のスレッド ローカル変数を宣言して特定の値に初期化します。

```cpp
__declspec( thread ) int tls_i = 1;  
```

スレッド ローカルのオブジェクトおよび変数を宣言するときは、以下のガイドラインに従う必要があります。

- 適用することができます、**スレッド**属性クラスとデータの宣言と定義にのみ**スレッド**関数宣言または定義では使用できません。

- 使用、**スレッド**干渉する可能性があります属性[遅延読み込み](../build/reference/linker-support-for-delay-loaded-dlls.md)DLL のインポートします。

- XP システムで**スレッド**DLL を使用して _declspec データが LoadLibrary 経由で動的に読み込まれる場合、正常に機能しない可能性があります。

- 指定することができます、**スレッド**静的ストレージ存続期間のあるデータ項目にのみ属性。 これには、グローバルなデータ オブジェクトが含まれます (両方**静的**と**extern**)、ローカルな静的オブジェクト、およびクラスの静的データ メンバーです。 使用して自動データ オブジェクトを宣言することはできません、**スレッド**属性。

- 使用する必要があります、**スレッド**スレッド ローカル オブジェクトの定義と宣言の属性の宣言と定義が同じファイルと別々 のファイルで発生するかどうか。

- 使用することはできません、**スレッド**型修飾子として属性。

- オブジェクトの宣言を使用するため、**スレッド**属性は許可されて、これら 2 つの例は同じ意味します。

    ```cpp
    // declspec_thread_2.cpp
    // compile with: /LD
    __declspec( thread ) class B {
    public:
       int data;
    } BObject;   // BObject declared thread local.

    class B2 {
    public:
       int data;
    };
    __declspec( thread ) B2 BObject2;   // BObject2 declared thread local.
    ```

- 標準 C では、自分自身への参照を含む式でオブジェクトや変数を初期化できます。ただし、この場合のオブジェクトは、非静的なものに限られます。 C++ では、通常、自分自身への参照を含む式でこのようにオブジェクトを動的に初期化できますが、この種の初期化はスレッド ローカル オブジェクトでは許可されません。 例:

    ```cpp
    // declspec_thread_3.cpp
    // compile with: /LD
    #define Thread __declspec( thread )
    int j = j;   // Okay in C++; C error
    Thread int tls_i = sizeof( tls_i );   // Okay in C and C++
    ```

     なお、 **sizeof**初期化されるオブジェクトを含む式自体への参照にはなりませんし、C および C++ では許可します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)  
[キーワード](../cpp/keywords-cpp.md)  
[スレッド ローカル ストレージ (TLS: Thread Local Storage)](../parallel/thread-local-storage-tls.md)

