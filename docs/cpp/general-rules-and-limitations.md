---
title: "一般的な規則と制約 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 一般的な規則と制約
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
  
-   **dllimport** 属性または `dllexport` 属性を指定しないで関数やオブジェクトを宣言した場合、その関数やオブジェクトは DLL インターフェイスの一部とは見なされません。  したがって、関数またはオブジェクトの定義は、該当のモジュール内か、同じプログラムの別のモジュール内に存在している必要があります。  関数やオブジェクトを DLL インターフェイスに含める場合は、その関数またはオブジェクトの定義を他のモジュールで `dllexport` として宣言する必要があります。  定義しない場合は、リンカー エラーが生成されます。  
  
     `dllexport` 属性を使用して関数やオブジェクトを宣言する場合、その定義は同じプログラムのどこかのモジュールに存在する必要があります。  定義しない場合は、リンカー エラーが生成されます。  
  
-   プログラムの 1 つのモジュールに、同じ関数またはオブジェクトの **dllimport** 宣言と `dllexport` 宣言の両方が含まれる場合は、`dllexport` 属性が **dllimport** 属性よりも優先されます。  ただし、コンパイラの警告が生成されます。  次に例を示します。  
  
    ```  
    __declspec( dllimport ) int i;  
    __declspec( dllexport ) int i;   // Warning; inconsistent;  
                                     // dllexport takes precedence.  
    ```  
  
-   C\+\+ では、グローバルに宣言されたポインターまたは静的なローカル データ ポインターを、**dllimport** 属性で宣言されたデータ オブジェクトのアドレスで初期化できます。これは、C ではエラーになります。  また、**dllimport** 属性で宣言された関数のアドレスで静的なローカル関数ポインターを初期化することもできます。  C では、このような代入で、関数のアドレスではなく、DLL インポート サンク \(関数に制御を移すコード スタブ\) のアドレスがポインターに設定されます。  C\+\+ では、ポインターに関数のアドレスが設定されます。  次に例を示します。  
  
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
  
     ただし、`dllexport` 属性が含まれたオブジェクト宣言のあるプログラムでは、そのプログラム内のどこかでそのオブジェクトを定義している必要があるため、グローバルな、またはローカルの静的な関数ポインターを、`dllexport` の関数のアドレスで初期化できます。  同様に、`dllexport` データ オブジェクトのアドレスで、グローバルまたはローカルの静的データ ポインターを初期化できます。  たとえば、次のコードの場合、C または C\+\+ でエラーは発生しません。  
  
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
  
-   通常のクラスとクラス テンプレートの特殊化の間でより一貫性のある `dllexport` の適用を可能にするために、Visual C\+\+ .NET には動作変更が加えられています。これにより、`dllexport` としてマークされていない基底クラスがを持つ通常のクラスに `dllexport` を適用すると、コンパイラで C4275 が発生します。  
  
     クラス テンプレートの特殊化が基底クラスである場合、コンパイラでも同じ警告が発生します。  この問題を回避するには、基底クラスに `dllexport` のマークを付けます。  クラス テンプレートの特殊化の場合、問題は **\_\_declspec\(dllexport\)** をどこに配置するかです。クラス テンプレートへのマーク付けは許可されていません。  代わりに、明示的にクラス テンプレートをインスタンス化し、この明示的にインスタンス化したクラスに `dllexport` のマークを付けます。  次に例を示します。  
  
    ```  
    template class __declspec(dllexport) B<int>;  
    class __declspec(dllexport) D : public B<int> {  
    // ...  
    ```  
  
     この回避策は、テンプレート引数が派生クラスの場合は失敗します。  次に例を示します。  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
     テンプレートではこれが一般的なパターンであるため、コンパイラでは、1 つ以上の基底クラスを持つクラスに `dllexport` が適用され、その基底クラスの 1 つ以上がクラス テンプレートの特殊化である場合の dllexport のセマンティックが変更されました。  このような場合、コンパイラはクラス テンプレートの特殊化に暗黙的に `dllexport` を適用します。  Visual C\+\+ .NET では、ユーザーは以下を実行でき、警告は発生しません。  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
## END Microsoft 固有の仕様  
  
## 参照  
 [dllexport、dllimport](../cpp/dllexport-dllimport.md)