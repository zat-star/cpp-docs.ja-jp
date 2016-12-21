---
title: "メンバー変数の追加ウィザード | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.variable.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "メンバー変数の追加ウィザード [C++]"
ms.assetid: 73e8fa99-ac1a-42e2-8fc2-4684b9eb6d4d
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# メンバー変数の追加ウィザード
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このウィザードでは、ヘッダー ファイルにメンバー変数宣言を追加し、指定したオプションに従って .cpp ファイルにコードを追加します。  このウィザードを使用してメンバー変数を追加すると、開発環境でそのコードを編集できます。  
  
 **\[アクセス\]**  
 メンバー変数へのアクセスを設定します。  アクセス修飾子とは、メンバー変数に対してほかのクラスが持つアクセス権を指定するキーワードです。  アクセス権の指定の詳細については、「[Member\-Access Control](../cpp/member-access-control-cpp.md)」を参照してください。  メンバー変数のアクセス レベルの既定の設定は public です。  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../Topic/protected%20\(C++\).md)  
  
-   [private](../Topic/private%20\(C++\).md)  
  
 **\[変数の型\]**  
 追加するメンバー変数の戻り値の型を設定します。  
  
-   ダイアログ ボックス コントロール以外のメンバー変数を追加する場合は、使用できる型の一覧から選択します。  
  
     戻り値の型については、「[Fundamental Types](../cpp/fundamental-types-cpp.md)」を参照してください。  
  
    |||  
    |-|-|  
    |`char`|**short**|  
    |**double**|`unsigned char`|  
    |**float**|`unsigned int`|  
    |`int`|`unsigned long`|  
    |**long**||  
  
-   ダイアログ ボックス コントロールのメンバー変数を追加する場合は、コントロールまたは値に対して返されるオブジェクトの型を入力します。  \[Control\] を選択すると、\[変数の種類\] は \[コントロール ID\] ボックスで選択したコントロールの基本クラスを指定します。  ダイアログ ボックス コントロールに値を 1 つ入力できる場合に **\[Value\]** を選択すると、\[変数の種類\] はコントロールに入力できる値の適切な型を指定します。  詳細については、「[ダイアログ ボックス コントロールおよび変数の型](../Topic/Dialog%20Box%20Controls%20and%20Variable%20Types.md)」を参照してください。  
  
     この値は \[コントロール ID\] での選択内容によって異なり、変更はできません。  
  
 **\[変数名\]**  
 追加するメンバー変数の名前を設定します。  通常、メンバー変数の先頭には "m\_" が付きます。これは既定の設定です。  
  
 **\[コントロール変数\]**  
 メンバー変数が[データ交換とデータ検証](../mfc/dialog-data-exchange-and-validation.md)をサポートするダイアログ ボックス内のコントロールを管理するように指定します。  詳細については、「[DoDataExchange](../Topic/CWnd::DoDataExchange.md)」を参照してください。  このオプションは、[CDialog](../mfc/reference/cdialog-class.md) の派生クラスに追加されたメンバー変数に対してだけ有効です。  \[コントロール ID\] オプションと \[コントロールの種類\] オプションをアクティブにするには、このボックスをオンにします。  
  
 **\[コントロール ID\]**  
 追加するコントロール変数の ID を設定します。  メンバー変数を追加するコントロールの型の ID を一覧から選択します。  \[コントロール変数\] ボックスがオンになっている場合だけ一覧がアクティブになり、既にダイアログ ボックスに追加されているコントロールの ID だけが表示されます。  たとえば、標準の **\[OK\]** ボタンのコントロール ID は **IDOK** です。  
  
|オプション|Description|  
|-----------|-----------------|  
|**Control**|このオプションはコントロールの型に既定で設定されます。  このオプションはコントロール自体を管理します。リスト ボックス、コンボ ボックス、またはエディット ボックスのようにコントロールの状態や内容は管理しません。|  
|**値**|このオプションは、エディット ボックスのように値を入力できるコントロール、チェック ボックスのように状態を反映できるコントロール、および範囲、内容、または状態を管理するコントロールに対してだけ有効です。  詳細については、「[ダイアログ ボックス コントロールおよび変数の型](../Topic/Dialog%20Box%20Controls%20and%20Variable%20Types.md)」を参照してください。|  
  
 **\[カテゴリ\]**  
 変数がコントロールの型に基づいているのか、それともコントロールの値に基づいているのかを指定します。  
  
 **\[コントロールの型\]**  
 追加するコントロールの型を設定します。  このボックスは変更できません。  たとえば、ボタン コントロールの型は **BUTTON** であり、コンボ ボックス コントロールの型は **COMBOBOX** です。  詳細については、「[ダイアログ ボックス コントロールおよび変数の型](../Topic/Dialog%20Box%20Controls%20and%20Variable%20Types.md)」を参照してください。  
  
 **\[最大文字数\]**  
 \[変数の種類\] が [CString](../atl-mfc-shared/reference/cstringt-class.md) に設定されている場合にだけ有効です。  コントロールに表示できる最大の文字数を示します。  
  
 **\[最小値\]**  
 変数の型が **BOOL**、`int`、**UINT**、**long**、`DWORD`、**float**、**double**、**BYTE**、**short**、[COLECurrency](../Topic/COleCurrency%20Class.md)、または [CTime](../Topic/CTime%20Class.md) の場合だけ有効です。  数値または日付の範囲として指定できる値の最小値を示します。  
  
 **\[最大値\]**  
 変数の型が **BOOL**、`int`、**UINT**、**long**、`DWORD`、**float**、**double**、**BYTE**、**short**、`COLECurrency`、または `CTime` の場合だけ有効です。  数値または日付の範囲として指定できる値の最大値を示します。  
  
 **\[.h ファイル\]**  
 メンバー変数にラッパー クラスが必要な ActiveX コントロール用です。  クラス宣言を追加するヘッダー ファイルの名前を設定します。  
  
 **\[.cpp ファイル\]**  
 メンバー変数にラッパー クラスが必要な ActiveX コントロール用です。  クラス定義を追加する実装ファイルの名前を設定します。  
  
 **\[コメント\]**  
 メンバー変数のヘッダー ファイルにコメントを挿入します。  
  
## 参照  
 [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)