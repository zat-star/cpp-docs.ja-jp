---
title: "方法: ADO.NET の VARIANT をマーシャリングする (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ADO.NET [C++], マーシャリング (VARIANT 型を)"
  - "VARIANT"
  - "VARIANT, マーシャリング"
ms.assetid: 67a180a7-5691-48ab-8d85-7f75a68dde91
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: ADO.NET の VARIANT をマーシャリングする (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

データベースにネイティブな `VARIANT` を追加する方法、およびデータベースの <xref:System.Object?displayProperty=fullName> をネイティブな `VARIANT` にマーシャリングする方法について説明します。  
  
## 使用例  
 この例では、ADO.NET <xref:System.Data.DataTable> オブジェクトとやり取りするための DatabaseClass というクラスが作成されます。  このクラスはネイティブな C\+\+ `class` です \(`ref class` や `value class` とは異なります\)。  これは、ネイティブ コードからこのクラスを使用するために必要なもので、マネージ型をネイティブ コードで使用することはできません。  このクラスは、クラスの宣言の前に `#pragma managed` ディレクティブが付いていることからわかるように、CLR を対象としてコンパイルされます。  このディレクティブの詳細については、「[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)」を参照してください。  
  
 DatabaseClass クラスのプライベート メンバーは `gcroot<DataTable ^> table` です。  ネイティブ型にはマネージ型は含まれないため、`gcroot` キーワードが必要です。  `gcroot` の詳細については、「[方法: ネイティブ型のハンドルを宣言する](../dotnet/how-to-declare-handles-in-native-types.md)」を参照してください。  
  
 この例のコードの他の部分は、`#pragma unmanaged` ディレクティブが `main` の前についていることからわかるように、ネイティブな C\+\+ コードです。  この例では、DatabaseClass の新しいインスタンスを作成し、そのメソッドを呼び出し、テーブルを作成してテーブルのいくつかの行を設定します。  ネイティブな `VARIANT` 型は、データベース列 ObjectCol の値として渡されます。  DatabaseClass 内では、<xref:System.Runtime.InteropServices?displayProperty=fullName> 名前空間にあるマーシャリング機能を使用して、これらの `VARIANT` 型がマネージ オブジェクトにマーシャリングされます。  具体的には、<xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A> メソッドは `VARIANT` を <xref:System.Object> にマーシャリングするときに、また <xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A> メソッドは <xref:System.Object> を `VARIANT` にマーシャリングするときに使用されます。  
  
```  
// adonet_marshal_variant.cpp  
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll  
#include <comdef.h>  
#include <gcroot.h>  
#include <iostream>  
using namespace std;  
  
#using <System.Data.dll>  
using namespace System;  
using namespace System::Data;  
using namespace System::Runtime::InteropServices;  
  
#define MAXCOLS 100  
  
#pragma managed  
class DatabaseClass  
{  
public:  
    DatabaseClass() : table(nullptr) { }  
  
    void AddRow(VARIANT *objectColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["ObjectCol"] = Marshal::GetObjectForNativeVariant(  
            IntPtr(objectColValue));  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("ObjectCol",  
            Type::GetType("System.Object"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(wchar_t *dataColumn, VARIANT *values,  
        int valuesLength)  
    {  
        // Marshal the name of the column to a managed  
        // String.  
        String ^columnStr = Marshal::PtrToStringUni(  
                (IntPtr)dataColumn);  
  
        // Get all rows in the table.  
        array<DataRow ^> ^rows = table->Select();  
        int len = rows->Length;  
        len = (len > valuesLength) ? valuesLength : len;  
        for (int i = 0; i < len; i++)  
        {  
            // Marshal each column value from a managed object  
            // to a VARIANT.  
            Marshal::GetNativeVariantForObject(  
                rows[i][columnStr], IntPtr(&values[i]));  
        }  
  
        return len;  
    }  
  
private:  
    // Using gcroot, you can use a managed type in  
    // a native class.  
    gcroot<DataTable ^> table;  
};  
  
#pragma unmanaged  
int main()  
{  
    // Create a table and add a few rows to it.  
    DatabaseClass *db = new DatabaseClass();  
    db->CreateAndPopulateTable();  
  
    BSTR bstr1 = SysAllocString(L"This is a BSTR in a VARIANT.");  
    VARIANT v1;  
    v1.vt = VT_BSTR;  
    v1.bstrVal = bstr1;  
    db->AddRow(&v1);  
  
    int i = 42;  
    VARIANT v2;  
    v2.vt = VT_I4;  
    v2.lVal = i;  
    db->AddRow(&v2);  
  
    // Now retrieve the rows and display their contents.  
    VARIANT values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"ObjectCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        switch (values[i].vt)  
        {  
            case VT_BSTR:  
                wcout << L"ObjectCol: " << values[i].bstrVal << endl;  
                break;  
            case VT_I4:  
                cout << "ObjectCol: " << values[i].lVal << endl;  
                break;  
            default:  
                break;  
        }  
  
    }  
  
    SysFreeString(bstr1);  
    delete db;  
  
    return 0;  
}  
```  
  
  **ObjectCol: This is a BSTR in a VARIANT.**  
**ObjectCol: 42**   
## コードのコンパイル  
  
-   コマンド ラインからコードをコンパイルするには、コード例を adonet\_marshal\_variant.cpp というファイルに保存し、次のステートメントを入力します。  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp  
    ```  
  
## .NET Framework セキュリティ  
 ADO.NET に関するセキュリティの詳細については、「[ADO.NET アプリケーションのセキュリティ保護](../Topic/Securing%20ADO.NET%20Applications.md)」を参照してください。  
  
## 参照  
 <xref:System.Runtime.InteropServices>   
 [データ アクセス](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](../Topic/ADO.NET.md)   
 [Interoperability](http://msdn.microsoft.com/ja-jp/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [ネイティブと .NET の相互運用性](../Topic/Native%20and%20.NET%20Interoperability.md)