---
title: "テクニカル ノート 59: MFC の MBCS/Unicode 変換マクロの使用 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.mbcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "変換マクロ [C++]"
  - "変換 (Unicode の)"
  - "マクロ [C++], MBCS 変換マクロ"
  - "MBCS [C++], 変換マクロ"
  - "MFCANS32.DLL"
  - "TN059"
  - "Unicode [C++], 変換マクロ"
  - "Unicode [C++], OLE インターフェイス"
ms.assetid: a2aab748-94d0-4e2f-8447-3bd07112a705
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# テクニカル ノート 59: MFC の MBCS/Unicode 変換マクロの使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。  結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。  最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 ここでは AFXPRIV.H.で定義されている MBCS\/Unicode の変換のマクロを使用する方法について説明します。  これらのマクロは、Unicode と MBCS を変換して、アプリケーションが OLE API を直接またはなんらかの理由に処理する場合は、一般に必要です。  
  
## 概要  
 MFC Version 3.x で、OLE インターフェイスが呼び出されたときに自動的に Unicode と MBCS の間で変換を行う場合は、特別な DLL \(MFCANS32.DLL\) が使用されました。  この DLL は常に Unicode であっても、OLE API およびインターフェイスが MBCS のように OLE アプリケーションが書き込まれるようにしたほとんど透明層です \(Macintosh では除きます\)。  このレイヤーがすぐに Win16 から Win32 に移植する便利な、許可されたアプリケーション \(MFC、Microsoft Word、Microsoft Excel と VBA は、このテクノロジを使用する Microsoft アプリケーションの一部ですが、重要なパフォーマンスがありました。  したがって、MFC 4.x はこの DLL を使用せず、Unicode OLE インターフェイスに直接話しません。  これを行うには、MFC は OLE インターフェイスを実装する場合、Unicode の MBCS に変換する呼び出しを OLE インターフェイスにすると、よく必要 MBCS に Unicode に変換する必要があります。  これを簡単かつ効率的に処理するには、いくつかのマクロには、この変換を簡単にするために作成されました。  
  
 マクロのこのような設定の作成の最大の難関の 1 つがメモリ割り当てです。  文字列に変換された設定されることはできないので、変換された結果を格納する新しいメモリを割り当てる必要があります。  これは、次のようなコードとした可能性があります:  
  
```  
// we want to convert an MBCS string in lpszA  
int nLen = MultiByteToWideChar(CP_ACP, 0,lpszA, -1, NULL, NULL);  
LPWSTR lpszW = new WCHAR[nLen];  
MultiByteToWideChar(CP_ACP, 0,   
   lpszA, -1, lpszW, nLen);  
// use it to call OLE here  
pI->SomeFunctionThatNeedsUnicode(lpszW);  
// free the string  
delete[] lpszW;  
```  
  
 一部の問題としてこのアプローチです。  主要な問題が書き込む、テストする多くのコードとデバッグです。  単純な関数の呼び出しで何か、より複雑です。  さらに、その一方で、重要なランタイム オーバーヘッドがあります。  メモリをヒープで変換を実行するたびに割り当てられ、解放する必要があります。  最後に、上記のコードは、追加されたこの変換が行われることなく\) に Unicode および Macintosh のビルド \(適切な `#ifdefs` 必要があります。  
  
 ここでは、表示するソリューションは 1\) マスクさまざまなプラットフォームの違い、および 2\) 使用効率的なメモリ割り当て方法、および 3\) が既存のソース・コードに挿入する簡単なマクロを作成します。  定義の 1 種類の例を次に示します。:  
  
```  
#define A2W(lpa) (\  
    ((LPCSTR)lpa == NULL) ? NULL : (\  
          _convert = (strnlen(lpa)+1),\  
        AfxA2WHelper((LPWSTR) alloca(_convert*2),   
      lpa, _convert)\  
    )\  
)  
```  
  
 上記のコードの代わりにこのマクロおよび操作を使用して非常に簡単です。:  
  
```  
// use it to call OLE here  
USES_CONVERSION;  
pI->SomeFunctionThatNeedsUnicode(T2OLE(lpszA));  
```  
  
 変換が必要でも、マクロを使用することは簡単で、有効な余分な呼び出しがあります。  
  
 各マクロの実装はヒープの代わりにスタックからメモリを割り当てるに \_alloca\(\) 関数を使用します。  スタックからメモリ割り当ては、ヒープ上のメモリを割り当てることより迅速、関数の終了時にメモリは自動的に解放されます。  また、マクロは **MultiByteToWideChar** \(または **WideCharToMultiByte**\) を呼び出すことを 1 回以上行われません。  これはいくつかはメモリを割り当てると、必要なよりされます。  これは MBC は最大で 1 **WCHAR** に変換し、各 **WCHAR** には、最大で 2 個の MBC バイトがあることがわかります。  少しだけでは必要に割り当てることによって、完全に常に変換関数への変換を番目は処理することができます。  ヘルパー関数 **AfxA2Whelper** の呼び出しは **MultiByteToWideChar** を直接呼び出す\) 変換を実行するために必要な引数のプッシュ数が減少します \(これは小さなコードでも発生します。  
  
 一時的な長さを格納する領域を持つマクロに対して変換マクロを使用する各関数でこれを行う\_convert というローカル変数を宣言する必要があります。  これは上記の例で参照されるように **USES\_CONVERSION** マクロの呼び出しで行われます。  
  
 一般的な変換マクロと OLE されたマクロがあります。  これら二つの異なるマクロ セットは、後で説明します。  マクロはすべて AFXPRIV.H.に存在します。  
  
## 一般的な変換マクロ  
 一般的な変換マクロは基になる機能を形成します。  前のセクションで、A2W が示すように、マクロの例と実装の 1 つがこのような「汎用」マクロです。  これは OLE とは無関係です。  一般的なマクロのセットは、次のものがあります。:  
  
```  
A2CW      (LPCSTR) -> (LPCWSTR)  
A2W      (LPCSTR) -> (LPWSTR)  
W2CA      (LPCWSTR) -> (LPCSTR)  
W2A      (LPCWSTR) -> (LPSTR)  
```  
  
 テキスト変換を行うだけでなく、`TEXTMETRIC`、`DEVMODE`、`BSTR`、OLE 割り当てられた文字列を変換するためのマクロとヘルパー関数があります。  これらのマクロは、この説明–の範囲を超える示します。これらのマクロの詳細については、" AFXPRIV.H になります。  
  
## OLE 変換マクロ  
 OLE 変換マクロは **OLESTR** の文字を使用する関数を処理するように設計されています。  OLE ヘッダーを調べると、**LPCOLESTR** と **OLECHAR**への複数の参照を参照します。  プラットフォームに固有ではない方法でこれらの型が OLE インターフェイスで使用される文字の種類を示すために使用されます。  **OLECHAR** は Win16 および Macintosh プラットフォームの `char` と Win32 の **WCHAR** に割り当てられます。  
  
 MFC で **\#ifdef** のディレクティブの数を保持するには、Where OLE 文字列複雑である各変換と同様のマクロがある最小にコード。  次のマクロは、一般に:  
  
```  
T2COLE   (LPCTSTR) -> (LPCOLESTR)  
T2OLE   (LPCTSTR) -> (LPOLESTR)  
OLE2CT   (LPCOLESTR) -> (LPCTSTR)  
OLE2T   (LPCOLESTR) -> (LPCSTR)  
```  
  
 さらに、`TEXTMETRIC`、`DEVMODE`、`BSTR`、OLE 割り当てられた文字列をも同様にマクロがあります。  詳細については AFXPRIV.H "を参照してください。  
  
## その他の注意事項  
 短いループでマクロを使用しないでください。  たとえば、次のコードの種類を記述する必要がありません:  
  
```  
void BadIterateCode(LPCTSTR lpsz)  
{  
   USES_CONVERSION;  
   for (int ii = 0; ii < 10000; ii++)  
      pI->SomeMethod(ii, T2COLE(lpsz));  
}  
```  
  
 上記のコードは、スタックにメモリの MB を割り当てることによって文字列 `lpsz` の内容が何であるかによってできます。  、ループの反復処理ごとに文字列を変換するのに時間がかかります。  代わりに、ループからこのような定数変換を移動する:  
  
```  
void MuchBetterIterateCode(LPCTSTR lpsz)  
{  
   USES_CONVERSION;  
   LPCOLESTR lpszT = T2COLE(lpsz);  
   for (int ii = 0; ii < 10000; ii++)  
      pI->SomeMethod(ii, lpszT);  
}  
```  
  
 文字列を設定していない場合は、関数にメソッドの呼び出しをカプセル化します。  これにより、変換バッファーを常に解放します。  たとえば、次のようになります。  
  
```  
void CallSomeMethod(int ii, LPCTSTR lpsz)  
{  
   USES_CONVERSION;  
   pI->SomeMethod(ii, T2COLE(lpsz));  
}  
  
void MuchBetterIterateCode2(LPCTSTR* lpszArray)  
{  
   for (int ii = 0; ii < 10000; ii++)  
      CallSomeMethod(ii, lpszArray[ii]);  
}  
```  
  
 戻り値が返される前にデータのコピーを作成しておくことを意味して、マクロの 1 種類の結果を返さないでください。  たとえば、このコードは低下します:  
  
```  
LPTSTR BadConvert(ISomeInterface* pI)  
{  
   USES_CONVERSION;  
   LPOLESTR lpsz = NULL;  
   pI->GetFileName(&lpsz);  
   LPTSTR lpszT = OLE2T(lpsz);  
   CoMemFree(lpsz);  
   return lpszT; // bad! returning alloca memory  
}  
```  
  
 上のコードは、値をコピーするものに戻り値を変更して、固定する:  
  
```  
CString BetterConvert(ISomeInterface* pI)  
{  
   USES_CONVERSION;  
   LPOLESTR lpsz = NULL;  
   pI->GetFileName(&lpsz);  
   LPTSTR lpszT = OLE2T(lpsz);  
   CoMemFree(lpsz);  
   return lpszT; // CString makes copy  
}  
```  
  
 マクロは使いやすく、コードに挿入やすいですが、上記の警告を確認できるように使用する場合は注意する必要があります。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)