---
title: 一般的な規則と制限事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 51f92844e993671a3423c04523ccf4e03f7f7e48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="general-rules-and-limitations"></a>一般的な規則と制約
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
  
-   関数を宣言またはオブジェクトにする場合、 **dllimport**または`dllexport`属性、関数またはオブジェクトは DLL インターフェイスの一部を考慮されません。 したがって、関数またはオブジェクトの定義は、該当のモジュール内か、同じプログラムの別のモジュール内に存在している必要があります。 関数やオブジェクトを DLL インターフェイスに含める場合は、その関数またはオブジェクトの定義を他のモジュールで `dllexport` として宣言する必要があります。 定義しない場合は、リンカー エラーが生成されます。  
  
     `dllexport` 属性を使用して関数やオブジェクトを宣言する場合、その定義は同じプログラムのどこかのモジュールに存在する必要があります。 定義しない場合は、リンカー エラーが生成されます。  
  
-   プログラムで 1 つのモジュールには、両方が含まれている場合**dllimport**と`dllexport`同じ関数またはオブジェクトの宣言、`dllexport`属性よりも優先、 **dllimport**属性です。 ただし、コンパイラの警告が生成されます。 例:  
  
    ```  
    __declspec( dllimport ) int i;  
    __declspec( dllexport ) int i;   // Warning; inconsistent;  
                                     // dllexport takes precedence.  
    ```  
  
-   C++ では、グローバルに宣言されたデータまたは静的ローカル データ ポインターを初期化することができますかで宣言されたデータ オブジェクトのアドレスを持つ、 **dllimport**属性は、c 言語でエラーが生成されますまたで宣言された関数のアドレスで静的ローカル関数ポインターを初期化することができます、 **dllimport**属性。 C では、このような代入で、関数のアドレスではなく、DLL インポート サンク (関数に制御を移すコード スタブ) のアドレスがポインターに設定されます。 C++ では、ポインターに関数のアドレスが設定されます。 例:  
  
    ```  
    __declspec( dllimport ) void func1( void );  
    __declspec( dllimport ) int i;  
  
    int *pi = &i;                             // Error in C  
    static void ( *pf )( void ) = &func1;     // Address of thunk in C,  
                                              // function in C++  
  
    void func2()  
    {  
       static int *pi = &i;                  // Error in C  
       static void ( *pf )( void ) = &func1; // Address of thunk in C,  
                                             // function in C++  
    }  
    ```  
  
     ただし、`dllexport` 属性が含まれたオブジェクト宣言のあるプログラムでは、そのプログラム内のどこかでそのオブジェクトを定義している必要があるため、グローバルな、またはローカルの静的な関数ポインターを、`dllexport` の関数のアドレスで初期化できます。 同様に、`dllexport` データ オブジェクトのアドレスで、グローバルまたはローカルの静的データ ポインターを初期化できます。 たとえば、次のコードの場合、C または C++ でエラーは発生しません。  
  
    ```  
    __declspec( dllexport ) void func1( void );  
    __declspec( dllexport ) int i;  
  
    int *pi = &i;                              // Okay  
    static void ( *pf )( void ) = &func1;      // Okay  
  
    void func2()  
    {  
        static int *pi = &i;                   // Okay  
        static void ( *pf )( void ) = &func1;  // Okay  
    }  
    ```  
  
-   適用する場合`dllexport`としてマークされていない基底クラスにある通常のクラスに`dllexport`、コンパイラで C4275 が生成されます。  
  
     クラス テンプレートの特殊化が基底クラスである場合、コンパイラでも同じ警告が発生します。 この問題を回避するには、基底クラスに `dllexport` のマークを付けます。 クラス テンプレートの特殊化の問題は、配置する場所、**方式**; をクラス テンプレートをマークすることはできません。 代わりに、明示的にクラス テンプレートをインスタンス化し、この明示的にインスタンス化したクラスに `dllexport` のマークを付けます。 例:  
  
    ```  
    template class __declspec(dllexport) B<int>;  
    class __declspec(dllexport) D : public B<int> {  
    // ...  
    ```  
  
     この回避策は、テンプレート引数が派生クラスの場合は失敗します。 例:  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
     テンプレートではこれが一般的なパターンであるため、コンパイラでは、1 つ以上の基底クラスを持つクラスに `dllexport` が適用され、その基底クラスの 1 つ以上がクラス テンプレートの特殊化である場合の dllexport のセマンティックが変更されました。 このような場合、コンパイラはクラス テンプレートの特殊化に暗黙的に `dllexport` を適用します。 次のでき、警告を取得できません。  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [dllexport、dllimport](../cpp/dllexport-dllimport.md)