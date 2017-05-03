---
title: "WRL 統合 (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3ad43894-c574-477c-ad3e-240301f381d4
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# WRL 統合 (C++/CX)
[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] \([!INCLUDE[cppwrl](../cppcx/includes/cppwrl-md.md)]\) コードを [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)] コードに自由に混在させることができます。 同じ翻訳単位では、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] のオブジェクトへのハンドル \(`^`\) 表記と [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)] のスマート ポインター \(`ComPtr<T>`\) 表記で宣言されたオブジェクトを使用できます。 ただし、戻り値、[!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)] HRESULT エラー コード、および [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 例外は、手動で処理する必要があります。  
  
## [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)] 開発  
 [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)] コンポーネントの作成と利用の詳細については、「[Windows ランタイム C\+\+ テンプレート ライブラリ \(WRL\)](http://msdn.microsoft.com/library/b915afce-553b-44a7-b8dc-0ab601758eb0)」を参照してください。  
  
## 例  
 次のコード スニペットは、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] と [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)] を使用して [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] クラスを利用し、メタデータ ファイルを調べます。  
  
 [Windows ストア アプリの構築フォーラム](http://social.msdn.microsoft.com/Forums/winappswithnativecode/thread/211ef583-db11-4e55-926b-6d9ab53dbdb4)のコード スニペットから引用した例。 このコード スニペットの作成者は、次の免責条項と条件を提示しています。  
  
1.  C\+\+ には [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型に反映させる特定の API が用意されていませんが、型の Windows メタデータ ファイル \(.winmd\) は CLR メタデータ ファイルに完全に準拠しています。 Windows は、指定された型の .winmd ファイルを取得するために新しいメタデータ検出 API \(RoGetMetaDataFile\) を提供しています。 ただし、クラスをインスタンス化できないため、これらの API は C\+\+ 開発者にはあまり役に立ちません。  
  
2.  コードをコンパイルした後、Runtimeobject.lib と Rometadata.lib をリンカーに渡す必要もあります。  
  
3.  このスニペットは現状のままで示されています。 正しく動作すると予測されますが、エラーが含まれている可能性もあります。  
  
```  
  
#include <hstring.h> #include <cor.h> #include <rometadata.h> #include <rometadataresolution.h> #include <collection.h> namespace ABI_Isolation_Workaround { #include <inspectable.h> #include <WeakReference.h> } using namespace ABI_Isolation_Workaround; #include <wrl/client.h> using namespace Microsoft::WRL; using namespace Windows::Foundation::Collections; IVector<String^>^ GetTypeMethods(Object^); MainPage::MainPage() { InitializeComponent(); Windows::Foundation::Uri^ uri = ref new Windows::Foundation::Uri("http://buildwindows.com/"); auto methods = GetTypeMethods(uri); std::wstring strMethods; std::for_each(begin(methods), end(methods), [&strMethods](../standard-library/string.md methodName) { strMethods += methodName->Data(); strMethods += L"\n"; }); wprintf_s(L"%s\n", strMethods.c_str()); } IVector<String^>^ GetTypeMethods(Object^ instance) { HRESULT hr; HSTRING hStringClassName; hr = instance->__cli_GetRuntimeClassName(reinterpret_cast<__cli_HSTRING__**>(&hStringClassName)); // internal method name subject to change post BUILD if (FAILED(hr)) __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD String^ className = reinterpret_cast<String^>(hStringClassName); ComPtr<IMetaDataDispenserEx> metadataDispenser;ComPtr<IMetaDataImport2> metadataImport;hr = MetaDataGetDispenser(CLSID_CorMetaDataDispenser, IID_IMetaDataDispenser, (LPVOID*)metadataDispenser.GetAddressOf()); if (FAILED(hr)) __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD HSTRING hStringFileName; mdTypeDef typeDefToken; hr = RoGetMetaDataFile(hStringClassName, metadataDispenser.Get(), &hStringFileName, &metadataImport, &typeDefToken); if (FAILED(hr)) __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD String^ fileName = reinterpret_cast<String^>(hStringFileName); HCORENUM hCorEnum = 0; mdMethodDef methodDefs[2048]; ULONG countMethodDefs = sizeof(methodDefs); hr = metadataImport->EnumMethods(&hCorEnum, typeDefToken, methodDefs, countMethodDefs,  &countMethodDefs); if (FAILED(hr)) __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD wchar_t methodName[1024]; ULONG countMethodName; std::wstring strMethods; Vector<String^>^ retVal = ref new Vector<String^>(); for(int i = 0; i < countMethodDefs; ++i) { countMethodName = sizeof(methodName); hr = metadataImport->GetMethodProps(methodDefs[i], nullptr, methodName, countMethodName, &countMethodName, nullptr, nullptr, nullptr, nullptr, nullptr); if (SUCCEEDED(hr)) { methodName[ countMethodName ] = 0; retVal->Append(ref new String(methodName)); } } return retVal; }  
  
```  
  
## 参照  
 [その他の言語との相互運用](../cppcx/interoperating-with-other-languages-c-cx.md)