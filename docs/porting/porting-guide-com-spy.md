---
title: "移植のガイド: COM Spy | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 24aa0d52-4014-4acb-8052-f4e2e4bbc3bb
caps.latest.revision: 10
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 移植のガイド: COM Spy
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックは、旧バージョンの Visual C\+\+ プロジェクトを Visual Studio の最新バージョンにアップグレードするプロセスについて説明する一連の記事の 2 番目です。  このトピックのコード例は、前回 Visual Studio 2005 でコンパイルされています。  
  
## COMSpy  
 COMSpy は、コンピューター上のサービス コンポーネントのアクティビティを監視してログに記録するプログラムです。  サービス コンポーネントは、システム上で実行し、同じネットワーク上のコンピューターで使用できる COM\+ コンポーネントです。  Windows コントロール パネルで、コンポーネント サービスの機能別に管理されています。  
  
### 手順 1.プロジェクト ファイルを変換する  
 プロジェクト ファイルは移行レポートを簡単に変換して生成します。  対処が必要な可能性がある問題について通知するエントリが、レポートにいくつかあります。  報告される 1 つの問題を示します \(このトピックでは、完全パスを削除するなど、エラー メッセージが読みやすさのために省略されることがあります\)。  
  
  **ComSpyAudit\\ComSpyAudit.vcproj: MSB8012: $\(TargetPath\) \('C:\\Users\\UserName\\Desktop\\spy\\spy\\ComSpyAudit\\.  \\XP32\_DEBUG\\ComSpyAudit.dll'\) does not match the Librarian's OutputFile property value '.  \\XP32\_DEBUG\\ComSpyAudit.dll' \('C:\\Users\\UserName\\Desktop\\spy\\spy\\XP32\_DEBUG\\ComSpyAudit.dll'\) in project configuration 'Unicode Debug&#124;Win32'.  これでは、プロジェクトのビルドが正しく行われない可能性があります。  これを修正するには、$\(TargetPath\) プロパティ値が %\(Lib.OutputFile\) で指定されている値に一致していることを確認してください。**  プロジェクトのアップグレードのよくある問題の 1 つとして、\[プロジェクトのプロパティ\] ダイアログ ボックスのリンカーの OutputFile の設定を検討しなければならないことがあります。  Visual Studio 2010 より前のプロジェクトでは、OutputFile が標準以外の値に設定されている場合、自動変換ウィザードで問題が発生する設定の 1 つです。  このケースでは、出力ファイルのパスが非標準のフォルダー XP32\_DEBUG に設定されていました。  このエラーの詳細について調べるために、vcbuild から msbuild へのかなりの変更を含むアップグレードである、Visual C 2010 プロジェクトのアップグレードに関連する[ブログの投稿](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx)を確認しました。  この情報によると、新しいプロジェクトを作成するときの出力ファイルの設定の既定値は $\(OutDir\)$\(TargetName\)$\(TargetExt\) ですが、これが変換されたプロジェクトでうまくいくことが確認できないため、これは変換時に設定されていません。  ただし、OutputFile でその設定にして、機能するか確認してみましょう。  機能すれば、続行できます。  非標準の出力フォルダーを使用する特段の理由がなければ、標準の場所を使用することをお勧めします。  このケースでは、移植とアップグレード プロセス中に、出力の場所を非標準のままにすることを選択しました。$ \(Outdir\) は、デバッグ構成で XP32\_DEBUG フォルダーに解決され、リリース構成では ReleaseU フォルダーに解決されます。  
  
### 手順 2.ビルドできる状態にする  
 移植されたプロジェクトをビルドすると、多数のエラーと警告が発生します。  
  
 次のコンパイラ エラーが原因で、ComSpyCtl はコンパイルを完了しません。  
  
  **atlcom.h\(611\): error C2664: 'HRESULT CComSpy::IPersistStreamInit\_Save\(LPSTREAM,BOOL,ATL::ATL\_PROPMAP\_ENTRY \*\)': cannot convert argument 3 from 'const ATL::ATL\_PROPMAP\_ENTRY \*' to 'ATL::ATL\_PROPMAP\_ENTRY \*'**  
**atlcom.h\(611\): note: Conversion loses qualifiers**  
**atlcom.h\(608\): note: while compiling class template member function 'HRESULT ATL::IPersistStreamInitImpl\<CComSpy\>::Save\(LPSTREAM,BOOL\)'**  
**\\spy\\spy\\comspyctl\\ccomspy.h\(28\): note: see reference to class template instantiation 'ATL::IPersistStreamInitImpl\<CComSpy\>' being compiled** エラーは atlcom.h の IPersistStreamInitImpl クラスの Save メソッドを参照します。  
  
```  
STDMETHOD(Save)(_Inout_ LPSTREAM pStm, _In_ BOOL fClearDirty)  
{  
T* pT = static_cast<T*>(this);  
ATLTRACE(atlTraceCOM, 2, _T("IPersistStreamInitImpl::Save\n"));  
return pT->IPersistStreamInit_Save(pStm, fClearDirty, T::GetPropertyMap());  
}  
```  
  
 問題は、古いバージョンのコンパイラが受け入れた変換が有効でなくなったことです。  C\+\+ 標準に準拠するために、以前許可されていたいくつかのコードが許可されなくなりました。  この場合、const ポインターを要求する関数に非定数のポインターを渡すことは安全ではありません。  解決策は、CComSpy クラスで IPersistStreamInit\_Save の宣言を検索し、3 番目のパラメーターに const 修飾子を追加することです。  
  
```  
HRESULT CComSpy::IPersistStreamInit_Save(LPSTREAM pStm, BOOL /* fClearDirty */, const ATL_PROPMAP_ENTRY* pMap)  
  
```  
  
 IPersistStreamInit\_Load にも同様の変更を加えます。  
  
```  
HRESULT IPersistStreamInit_Load(LPSTREAM pStm, const ATL_PROPMAP_ENTRY* pMap);  
```  
  
 次のエラーでは、登録を扱っています。  
  
  **error MSB3073: The command "regsvr32 \/s \/c "C:\\Users\\username\\Desktop\\spy\\spy\\ComSpyCtl\\.  \\XP32\_DEBUG\\ComSpyCtl.lib"**  
**error MSB3073: echo regsvr32 exec.  time \> ".  \\XP32\_DEBUG\\regsvr32.trg"**  
**error MSB3073:**  
**error MSB3073: :VCEnd" exited with code 3.**  このビルド後の登録コマンドはもう必要ありません。  代わりに、カスタム ビルド コマンドを削除して、リンカー設定で出力を登録するよう指定します。  
  
### 警告に対処する  
 プロジェクトで次のリンカー警告が生成されます。  
  
  **warning LNK4075: ignoring '\/EDITANDCONTINUE' due to '\/SAFESEH' specification** \/SAFESEH コンパイラ オプションはデバッグ モード \(\/EDITANDCONTINUE が有効なとき\) では役に立たないので、ここでは、デバッグの構成でのみ、\/SAFESEH を無効にします。  \[プロパティ\] ダイアログでこれを行うには、このエラーを生成するプロジェクトの \[プロパティ\] ダイアログを開き、まず \[構成\] を \[デバッグ\] に設定して \(実際は Unicode のデバッグ\)、\[リンカー高度クラス\] セクションで、\[安全な例外ハンドラーを含むイメージ\] プロパティを \[いいえ\] に設定 \(\/SAFESEH:NO\) します。  
  
 コンパイラは PROP\_ENTRY\_EX が廃止されていることを警告します。  これは安全でなく、推奨される代替手段は PROP\_ENTRY\_TYPE\_EX です。  
  
```  
BEGIN_PROPERTY_MAP(CComSpy)  
PROP_ENTRY_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy)  
PROP_ENTRY_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy)  
PROP_ENTRY_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy)  
PROP_ENTRY_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy)  
PROP_PAGE(CLSID_StockFontPage)  
END_PROPERTY_MAP()  
```  
  
 ccomspy.h 内のコードをそれに応じて変更し、COM 型を適宜追加します。  
  
```  
BEGIN_PROPERTY_MAP(CComSpy)  
PROP_ENTRY_TYPE_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy, VT_BSTR)  
PROP_ENTRY_TYPE_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)  
PROP_ENTRY_TYPE_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)  
PROP_ENTRY_TYPE_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy, VT_UINT)  
PROP_PAGE(CLSID_StockFontPage)  
END_PROPERTY_MAP()  
```  
  
 最後の警告に来ていますが、これはより厳密なコンパイラの一致チェックも原因になっています。  
  
  **\\spy\\comspyctl\\usersub.h\(70\): warning C4457: declaration of 'var' hides function parameter**  
**\\spy\\comspyctl\\usersub.h\(48\): note: see declaration of 'var'**  
**\\spy\\comspyctl\\usersub.h\(94\): warning C4018: '\<': signed\/unsigned mismatch**  
 **ComSpy.cpp**  
**\\spy\\comspyctl\\comspy.cpp\(186\): warning C4457: declaration of 'bHandled' hides function parameter**  
**\\spy\\spy\\comspyctl\\comspy.cpp\(177\): note: see declaration of 'bHandled'** 警告 C4018 は次のコードに由来します。  
  
```  
for (i=0;i<lCount;i++)  
    CoTaskMemFree(pKeys[i]);  
```  
  
 問題は、i が UINT として宣言され、lCount が long として宣言されているため、符号付き\/符号なしの不一致があることです。  lCount の型を UINT に変更するのは便利ではありません。なぜなら、long 型を使用し、ユーザーのコード内にはない IMtsEventInfo::get\_Count から値を取得しているためです。  したがって、コードにキャストを追加します。  C スタイルのキャストは、このような数値のキャストに対して機能しますが、static\_cast が推奨されるスタイルです。  
  
```  
for (i=0;i<static_cast<UINT>(lCount);i++)  
    CoTaskMemFree(pKeys[i]);  
```  
  
 これらの警告は、同じ名前を持つパラメーターがある関数で変数が宣言されている場合に発生し、混乱しやすいコードになる可能性があます。  ローカル変数の名前を変更することで、これを修正します。  
  
```  
  
```  
  
### 手順 3.テストおよびデバッグを行う  
 まずさまざまなメニューやコマンドを使用して実行し、それからアプリケーションを終了することでアプリケーションをテストしました。  指摘された唯一の問題は、アプリを閉じる時に使用したデバッグのアサーションでした。  問題は、アプリケーションのメインの COM コンポーネントである CSpyCon オブジェクトの基本クラスの CWindowImpl のデストラクターに表示されました。  Atlwin.h 内の次のコードで、アサーション エラーが発生しました。  
  
```  
virtual ~CWindowImplRoot()  
{  
#ifdef _DEBUG  
if(m_hWnd != NULL)// should be cleared in WindowProc  
{  
ATLTRACE(atlTraceWindowing, 0, _T("ERROR - Object deleted before window was destroyed\n"));  
ATLASSERT(FALSE);  
}  
#endif //_DEBUG  
}  
```  
  
 hWnd は通常、WindowProc 関数で 0 に設定されますが、既定の WindowProc の代わりに、ウィンドウを閉じる Windows メッセージ \(WM\_SYSCOMMAND\) でカスタム ハンドラーが呼び出されることが原因で発生したのではありません。  カスタム ハンドラーは hWnd をゼロに設定していませんでした。  MFC の CWnd クラスの同様のコードを見ると、ウィンドウが破棄されると OnNcDestroy が呼び出され、MFC ではCWnd::OnNcDestroy をオーバーライドするときに、ウィンドウのハンドルをウィンドウから分離することを含め、基本 NcDestroy を呼び出して適切なクリーンアップ操作が必ず発生するようにする、つまり、hWnd をゼロに設定するようドキュメントでアドバイスされています。  このアサーションは、同じアサーション コードが古いバージョンの atlwin.h に存在するため、元のバージョンのサンプルでもトリガーされている可能性があります。  
  
 アプリの機能をテストするために、ATL プロジェクト テンプレートを使用したサービス コンポーネントを作成し、ATL プロジェクト ウィザードで COM\+ のサポートを追加することを選択しました。  サービス コンポーネントの作業をこれまで行ったことがなくても、作成は難しくなく、ほかのアプリが使用するシステムやネットワークでも登録して利用できます。  COM Spy アプリは、診断を目的としてサービス コンポーネントのアクティビティを監視するよう設計されています。  
  
 次に、クラスを追加して ATL オブジェクトを選択し、オブジェクト名を Dog と指定しました。  そして、dog.h および dog.cpp に実装を追加しました。  
  
```  
STDMETHODIMP CDog::Wag(LONG* lDuration)  
{  
    // TODO: Add your implementation code here  
    *lDuration = 100l;  
    return S_OK;  
}  
```  
  
 次に、ビルドして登録し \(Visual Studio を管理者として実行する必要があります\)、Windows コントロール パネルのサービス コンポーネント アプリケーションを使用してアクティブ化しました。  C\# Windows フォーム プロジェクトを作成し、ツールボックスからフォームにボタンをドラッグして、クリック イベント ハンドラーをダブルクリックしました。  次のコードを追加し、Dog コンポーネントのインスタンスを作成しました。  
  
```  
private void button1_Click(object sender, EventArgs e)  
{  
    ATLProjectLib.Dog dog1 = new ATLProjectLib.Dog();  
    dog1.Wag();  
}  
```  
  
 これは問題なく実行できました。COM Spy が起動して実行され、Dog コンポーネントを監視するよう構成されると、アクティビティを示す大量のデータが表示されます。  
  
## 参照  
 [移植およびアップグレード: 例とケース スタディ](../porting/porting-and-upgrading-examples-and-case-studies.md)   
 [次の例: Spy\+\+](../Topic/Porting%20Guide:%20Spy++.md)   
 [前の例: MFC Scribble](../porting/porting-guide-mfc-scribble.md)