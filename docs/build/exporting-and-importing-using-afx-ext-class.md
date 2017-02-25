---
title: "AFX_EXT_CLASS を使ったエクスポート/インポート | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "afx_ext_class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFX_EXT_CLASS マクロ"
  - "実行可能ファイル [C++], インポート (クラスを)"
  - "エクスポート (クラスを) [C++]"
  - "エクスポート (DLL を) [C++], AFX_EXT_CLASS マクロ"
  - "拡張 DLL [C++], エクスポート (クラスを)"
  - "インポート (DLL を) [C++]"
ms.assetid: 6b72cb2b-e92e-4ecd-bcab-c335e1d1cfde
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# AFX_EXT_CLASS を使ったエクスポート/インポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[拡張 DLL](../build/extension-dlls-overview.md) は **AFX\_EXT\_CLASS** マクロを使用してクラスをエクスポートします。拡張 DLL にリンクした実行可能ファイルは、このマクロを使用してクラスをインポートします。  **AFX\_EXT\_CLASS** マクロを使うと、拡張 DLL のビルドに使われた同じヘッダー ファイルをその DLL とリンクする実行形式で使うことができます。  
  
 DLL のヘッダー ファイルで、次のように **AFX\_EXT\_CLASS** キーワードをクラス宣言に追加します。  
  
```  
class AFX_EXT_CLASS CMyClass : public CDocument  
{  
// <body of class>  
};  
```  
  
 このマクロは、プリプロセッサ シンボルの **\_AFXDLL** および `_AFXEXT` が定義されている場合は、MFC により **\_\_declspec\(dllexport\)** として定義されます。  **\_AFXDLL** が定義されていて `_AFXEXT` が定義されていない場合は、**\_\_declspec\(dllimport\)** として定義されます。  プリプロセッサ シンボルの **\_AFXDLL** が定義されているということは、MFC の共有バージョンがターゲットの実行形式 \(DLL またはアプリケーション\) によって使用されていることを示します。  **\_AFXDLL** および `_AFXEXT` が定義されているいうことは、ターゲットの実行形式は拡張 DLL であることを示します。  
  
 拡張 DLL からエクスポートする場合は、**AFX\_EXT\_CLASS** は **\_\_declspec\(dllexport\)** として定義されるので、.def ファイル内のクラスのすべてのシンボルに対応する装飾名を記述しなくても、すべてのクラスをエクスポートできます。  この方法は、MFC サンプル [DLLHUSK](http://msdn.microsoft.com/ja-jp/dfcaa6ff-b8e2-4efd-8100-ee3650071f90) で使用されています。  
  
 この方法を使うと、.def ファイルとすべてのクラスの装飾名を作成せずに済みます。ただし、.def ファイルを作成する方が、名前が序数でエクスポートされるので効率的です。  .def ファイルを使ってエクスポートを行うには、ヘッダー ファイルの先頭と末尾に次のコードを追加します。  
  
```  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
> [!CAUTION]
>  インライン関数はバージョン間での不整合の可能性があるため、エクスポートする場合は注意してください。  インライン関数は、アプリケーション コード内に展開されます。このため、関数を書き直した場合は、アプリケーション自体をコンパイルし直さないと、インライン関数は更新されません。  通常、DLL 関数は、関数を使うアプリケーションをビルドし直さなくても更新できます。  
  
## クラスの個別のメンバーのエクスポート  
 クラスのメンバーを個別にエクスポートすることもできます。  たとえば、`CDialog` 派生クラスをエクスポートする場合、エクスポートする必要があるのはコンストラクターと `DoModal` 呼び出しだけです。  このような場合は、エクスポートする各メンバーに対して **AFX\_EXT\_CLASS** を使用します。  
  
 たとえば、次のようになります。  
  
```  
class CExampleDialog : public CDialog  
{  
public:  
   AFX_EXT_CLASS CExampleDialog();  
   AFX_EXT_CLASS int DoModal();  
   ...  
   // rest of class definition  
   ...  
};  
```  
  
 クラスの一部のメンバーのみがエクスポートされるため、MFC マクロの動作に起因する別の問題が生じる可能性もあります。  MFC のいくつかのヘルパー マクロは、実際にデータ メンバーを宣言または定義しています。  このため、これらのデータ メンバーも DLL からエクスポートされる必要があります。  
  
 たとえば、拡張 DLL をビルドする場合、`DECLARE_DYNAMIC` マクロは次のように定義されます。  
  
```  
#define DECLARE_DYNAMIC(class_name) \  
protected: \  
   static CRuntimeClass* PASCAL _GetBaseClass(); \  
public: \  
   static AFX_DATA CRuntimeClass class##class_name; \  
   virtual CRuntimeClass* GetRuntimeClass() const; \  
```  
  
 static `AFX_DATA` で始まる行は、クラス内部のスタティック オブジェクトを宣言しています。  このクラスを適切にエクスポートし、クライアントの実行形式からそのクラスのランタイム情報にアクセスするには、このスタティック オブジェクトをエクスポートする必要があります。  この静的オブジェクトは修飾子 `AFX_DATA` を付けて宣言されているため、DLL をビルドする場合は `AFX_DATA` を **\_\_declspec\(dllexport\)** として定義し、クライアント実行可能ファイルをビルドする場合は **\_\_declspec\(dllimport\)** として定義するだけで済みます。  **AFX\_EXT\_CLASS** は既に同じ方法で定義されているので、クラスの定義について `AFX_DATA` を **AFX\_EXT\_CLASS** と同じように定義し直すだけで済みます。  
  
 たとえば、次のようになります。  
  
```  
#undef  AFX_DATA  
#define AFX_DATA AFX_EXT_CLASS  
  
class CExampleView : public CView  
{  
   DECLARE_DYNAMIC()  
   // ... class definition ...  
};  
  
#undef  AFX_DATA  
#define AFX_DATA  
```  
  
 MFC は、マクロ内で定義するデータ項目にシンボル `AFX_DATA` を常に使うので、この手法はこのようなすべての状況で使うことができます。  たとえば、`DECLARE_MESSAGE_MAP` にも使うことができます。  
  
> [!NOTE]
>  選択したクラス メンバーではなく、クラス全体をエクスポートする場合、静的データ メンバーは自動的にエクスポートされます。  
  
### 目的に合ったトピックをクリックしてください  
  
-   [.def ファイルを使った DLL からのエクスポート](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [\_\_declspec\(dllexport\) を使った DLL からのエクスポート](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [C 言語の実行形式で使う C\+\+ 関数のエクスポート](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C\/C\+\+ 言語の実行形式で使う C 関数のエクスポート](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [エクスポート方式の使い分け](../build/determining-which-exporting-method-to-use.md)  
  
-   [\_\_declspec\(dllimport\) を使ったアプリケーションへのインポート](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL の初期化](../build/initializing-a-dll.md)  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [装飾名](../Topic/Decorated%20Names.md)  
  
-   [インライン関数のインポートとエクスポート](../Topic/Importing%20and%20Exporting%20Inline%20Functions.md)  
  
-   [相互インポート](../Topic/Mutual%20Imports.md)  
  
## 参照  
 [DLL からのエクスポート](../build/exporting-from-a-dll.md)