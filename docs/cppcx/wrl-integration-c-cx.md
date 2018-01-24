---
title: "WRL 統合 (C + + CX) |Microsoft ドキュメント"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ad43894-c574-477c-ad3e-240301f381d4
caps.latest.revision: "9"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 859a25f4fc9698899f1139038e161d28da06220e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="wrl-integration-ccx"></a>WRL 統合 (C++/CX)

自由に混在させることによる WRL コード[!INCLUDE[cppwrl](includes/cppwrl-md.md)] ([!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)]) コード。 同じ翻訳単位、WRL のオブジェクトへのハンドルで宣言されたオブジェクトを使用することができます (`^`) 表記と[!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)]スマート ポインター (`ComPtr<T>`) 表記します。 、、の戻り値が手動で処理する必要がありますと[!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)]HRESULT エラー コードと WRL 例外。
  
## <a name="includecppwrlshortincludescppwrl-short-mdmd-development"></a>[!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)] 開発

作成と利用の詳細については[!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)]コンポーネントを参照して[Windows ランタイム C++ テンプレート ライブラリ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)です。

### <a name="example"></a>例

次のコード スニペットでは、WRL を使用する方法を示しますと[!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)]を使用する[!INCLUDE[wrt](includes/wrt-md.md)]クラスし、メタデータ ファイルを調べます。

例が内のコード スニペットから引用した、[構築 Windows ストア アプリのフォーラム](http://social.msdn.microsoft.com/Forums/winappswithnativecode/thread/211ef583-db11-4e55-926b-6d9ab53dbdb4)です。 このコード スニペットの作成者は、次の免責条項と条件を提示しています。

1. C++ には [!INCLUDE[wrt](includes/wrt-md.md)] 型に反映させる特定の API が用意されていませんが、型の Windows メタデータ ファイル (.winmd) は CLR メタデータ ファイルに完全に準拠しています。 Windows は、指定された型の .winmd ファイルを取得するために新しいメタデータ検出 API (RoGetMetaDataFile) を提供しています。 ただし、クラスをインスタンス化できないため、これらの API は C++ 開発者にはあまり役に立ちません。

1. コードをコンパイルした後、Runtimeobject.lib と Rometadata.lib をリンカーに渡す必要もあります。

1. このスニペットは現状のままで示されています。 正しく動作すると予測されますが、エラーが含まれている可能性もあります。

```cpp
#include <hstring.h>
#include <cor.h>
#include <rometadata.h>
#include <rometadataresolution.h>
#include <collection.h>

namespace ABI_Isolation_Workaround {
    #include <inspectable.h>
    #include <WeakReference.h>
}
using namespace ABI_Isolation_Workaround;
#include <wrl/client.h>

using namespace Microsoft::WRL;
using namespace Windows::Foundation::Collections;

IVector<String^>^ GetTypeMethods(Object^);

MainPage::MainPage()
{
    InitializeComponent();

    Windows::Foundation::Uri^ uri = ref new Windows::Foundation::Uri("http://buildwindows.com/");
    auto methods = GetTypeMethods(uri);

    std::wstring strMethods;
    std::for_each(begin(methods), end(methods), [&strMethods](String^ methodName) {
        strMethods += methodName->Data();
        strMethods += L"\n";
    });

    wprintf_s(L"%s\n", strMethods.c_str());
}

IVector<String^>^ GetTypeMethods(Object^ instance)
{
    HRESULT hr;
    HSTRING hStringClassName;
    hr = instance->__cli_GetRuntimeClassName(reinterpret_cast<__cli_HSTRING__**>(&hStringClassName)); // internal method name subject to change post BUILD
    if (FAILED(hr))
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD
    String^ className = reinterpret_cast<String^>(hStringClassName);

    ComPtr<IMetaDataDispenserEx> metadataDispenser; ComPtr<IMetaDataImport2> metadataImport; hr = MetaDataGetDispenser(CLSID_CorMetaDataDispenser, IID_IMetaDataDispenser, (LPVOID*)metadataDispenser.GetAddressOf());
    if (FAILED(hr))
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD

    HSTRING hStringFileName;
    mdTypeDef typeDefToken;
    hr = RoGetMetaDataFile(hStringClassName, metadataDispenser.Get(), &hStringFileName, &metadataImport, &typeDefToken);
    if (FAILED(hr))
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD
    String^ fileName = reinterpret_cast<String^>(hStringFileName);

    HCORENUM hCorEnum = 0;
    mdMethodDef methodDefs[2048];
    ULONG countMethodDefs = sizeof(methodDefs);
    hr = metadataImport->EnumMethods(&hCorEnum, typeDefToken, methodDefs, countMethodDefs,  &countMethodDefs);
    if (FAILED(hr))
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD

    wchar_t methodName[1024];
    ULONG countMethodName;
    std::wstring strMethods;
    Vector<String^>^ retVal = ref new Vector<String^>();

    for (int i = 0; i < countMethodDefs; ++i)
    {
        countMethodName = sizeof(methodName);
        hr = metadataImport->GetMethodProps(methodDefs[i], nullptr, methodName, countMethodName, &countMethodName, nullptr, nullptr, nullptr, nullptr, nullptr);
        if (SUCCEEDED(hr))
        {
            methodName[ countMethodName ] = 0;
            retVal->Append(ref new String(methodName));
        }
    }
    return retVal;
}

```

## <a name="see-also"></a>関連項目

[その他の言語と相互運用](interoperating-with-other-languages-c-cx.md)  
