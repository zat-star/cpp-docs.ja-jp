---
title: "リンカ ツール エラー LNK2005 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2005
dev_langs:
- C++
helpviewer_keywords:
- LNK2005
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 40097ea2b5c5519a5b883aad09788cf2f802ea36
ms.contentlocale: ja-jp
ms.lasthandoff: 05/10/2017

---
# <a name="linker-tools-error-lnk2005"></a>リンカ ツール エラー LNK2005
*シンボル*オブジェクトで既に定義されています。  
  
シンボル*シンボル*も複数回定義されました。   
  
このエラーの致命的なエラーが続く[LNK1169](../../error-messages/tool-errors/linker-tools-error-lnk1169.md)です。  
  
### <a name="possible-causes-and-solutions"></a>考えられる原因と解決策  
  
通常、このエラーは、解除した場合、*単一定義規則*、外部から参照できるオブジェクトまたは関数の実行可能ファイル全体で任意に使用されるテンプレート、関数、型、または指定されたオブジェクト ファイル内のオブジェクトの 1 つだけの定義と 1 つだけ定義できます。  
  
このエラーの一般的な原因を示します。  
  
-   このエラーは、ヘッダー ファイルの変数を定義するときに発生することができます。 たとえば、プロジェクトで 1 つ以上のソース ファイルでこのヘッダー ファイルをインクルードする場合、エラーが発生します。  
  
    ```h  
    // LNK2005_global.h  
    int global_int;  // LNK2005
    ```  
  
    次の解決策が考えられます。  
  
    -   変数を宣言して`extern`ヘッダー ファイル:`extern int global_int;`指定してから、および必要に応じて、1 つのソース ファイル内で初期化:`int global_int = 17;`です。 この変数がグローバルに宣言することで、任意のソース ファイルで使用できること`extern`など、ヘッダー ファイルをインクルードします。 変数グローバルに適用する必要がありますが、このソリューションを推奨しますが、優れたソフトウェア エンジニア リングのプラクティスには、グローバル変数が最小限に抑えられます。  
    
    -   変数を宣言して[静的](../../cpp/storage-classes-cpp.md#static):`static int static_int = 17;`です。 これを現在のオブジェクト ファイルに定義のスコープを制限し、変数の独自のコピーが複数のオブジェクト ファイルできます。 ヘッダー ファイルで静的変数を定義するグローバル変数と混同する可能性のためお勧めしません。 必要に応じてそれらを使用するソース ファイルに定義する静的変数を移動します。  
  
    -   変数を宣言して[selectany](../../cpp/selectany.md):`__declspec(selectany) int global_int = 17;`です。 これは、すべての外部参照で使用するための 1 つの定義を選択し、残りの部分を破棄するリンカーを示しています。 このソリューションのインポート ライブラリを結合するときになる状況があります。 それ以外の場合、お勧めしません、リンカー エラーを回避する手段として。  
  
-   このエラーは、ヘッダー ファイルがない関数を定義するときに発生する可能性が`inline`です。 1 つ以上のソース ファイルにこのヘッダー ファイルを含めると、実行可能ファイルで、関数の複数の定義を取得します。  
    
    ```h  
    // LNK2005_func.h  
    int sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```  
  
    次の解決策が考えられます。  
  
    -   追加、`inline`関数キーワード。 

        ```h  
        // LNK2005_func_inline.h  
        inline int sample_function(int k) { return 42 * (k % 167); }  
        ```  
  
    -   ヘッダー ファイルから、関数本体を削除し、宣言のみのままにして、1 つのソース ファイル内の関数を実装します。  
  
        ```h  
        // LNK2005_func_decl.h  
        int sample_function(int);  
        ```  
  
        ```cpp  
        // LNK2005_func_impl.cpp  
        int sample_function(int k) { return 42 * (k % 167); }  
        ```  
-   このエラーは、ヘッダー ファイルで、クラス宣言の外側のメンバー関数を定義する場合にも発生することができます。  
  
    ```h  
    // LNK2005_member_outside.h  
    class Sample {
    public:
        int sample_function(int);  
    };
    int Sample::sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```  
  
    この問題を解決するには、クラス内のメンバー関数の定義を移動します。 クラス宣言内で定義されたメンバー関数が暗黙的にインライン展開ではありません。  
  
    ```h  
    // LNK2005_member_inline.h  
    class Sample {
    public:
        int sample_function(int k) { return 42 * (k % 167); }  
    };
    ```  
  
-   このエラーは、1 つ以上のバージョンの標準ライブラリまたは CRT にリンクする場合に発生することができます。 たとえば場合両方、小売およびデバッグ CRT ライブラリ、または、ライブラリの静的および動的な両方のバージョンまたは標準ライブラリの 2 つの異なるバージョンを実行可能ファイルにリンクしようとすると、このエラー可能性があります報告何度も。 この問題を解決するには、リンク コマンドから各ライブラリのすべてが 1 つのコピーを削除します。 製品版を混在させるし、ライブラリ、または別のバージョンの同じ実行可能ファイルで、ライブラリのデバッグはお勧めできません。  
  
    コマンド ラインで、既定以外のライブラリを使用するようにリンカーに指示するには、使用、および使用するライブラリを指定、 [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)既定のライブラリを無効にするオプションです。 IDE を使用して開くライブラリを指定するようにプロジェクトへの参照を追加、**プロパティ ページ**で、プロジェクトのダイアログ ボックス、**リンカー**、**入力**プロパティ ページで設定するか**すべての既定のライブラリの無視**、または**固有の既定のライブラリの無視**プロパティを既定のライブラリを無効にします。   
  
-   このエラーは、使用すると、静的および動的なライブラリの使用を混在している場合に発生することができます、 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)オプション。 たとえば、作成、使用する DLL を実行可能ファイルで、静的な CRT にリンクしている場合は、このエラーが発生することができます。 この問題を解決するには、実行可能ファイルで使用するビルドのすべてのライブラリおよび実行可能ファイルの全体のスタティック ライブラリのみまたはダイナミック ライブラリのみを使用します。  
  
-   シンボルがパッケージ化された関数の場合、このエラーが発生することができます (使用してコンパイルした[/Gy](../../build/reference/gy-enable-function-level-linking.md))、1 つ以上のファイルに含まれていましたは、コンパイルの間で変更されました。 この問題を修正するのには、パッケージ化された関数が含まれているすべてのファイルを再コンパイルします。  
  
-   このエラーは、異なる方法で、さまざまなライブラリで 2 つのメンバー オブジェクトのシンボルを定義し、両方のメンバー オブジェクトが使用する場合に発生します。 ライブラリが静的にリンクされている場合は、この問題を解決する方法の 1 つが、1 つだけのライブラリからメンバー オブジェクトを使用して、そのライブラリをリンカーのコマンドラインで最初に含まれます。 両方のシンボルを使用するのには、それらを区別する方法を作成する必要があります。 たとえば、ソースからのライブラリをビルドする場合は、一意の名前空間では、各ライブラリをラップできます。 また、一意の名前を使用して、元のライブラリのいずれかへの参照をラップし、元のライブラリに新しいライブラリをリンクして、実行可能ファイルを元のライブラリではなく、新しいライブラリにリンクする新しいラッパー ライブラリを作成できます。  
  
-   場合に、このエラーが発生することができます、`extern const`変数が 2 回定義され、それぞれの定義で別の値を持ちます。 この問題を修正するには、一度だけ定数を定義または名前空間を使用または`enum class`定数を区別するために定義します。  
  
-   Uuid.lib を Guid (oledb.lib や adsiid.lib など) を定義するその他の .lib ファイルと組み合わせて使用する場合、このエラーが発生することができます。 例:  
  
    ```Output  
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject  
    already defined in uuid.lib(go7.obj)  
    ```  
  
     この問題を解決するには追加[/FORCE:MULTIPLE](../../build/reference/force-force-file-output.md)その uuid.lib が最初に参照されるライブラリがリンカーのコマンド ライン オプション、および確認してください。
  
## <a name="additional-information"></a>追加情報  
  
以前のバージョンのツールセットを使用している場合は、このエラーの原因を特定の詳細については次のサポート技術情報記事を参照してください。  
  
-   [Visual C で間違った順序で CRT ライブラリおよび MFC ライブラリがリンクされている LNK2005 エラーが発生します。](https://support.microsoft.com/kb/148652)  
  
-   [修正: Global Overloaded Delete Operator 原因 LNK2005](https://support.microsoft.com/kb/140440)  
  
-   [Visual c ATL 実行可能 (.exe) プロジェクトをコンパイルするときに LNK2005 エラーが発生した](https://support.microsoft.com/kb/184235)です。  
  

