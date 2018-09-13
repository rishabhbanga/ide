# Generate API in Wizard Mode {#concept_cgn_txh_r2b .concept}

This article will introduce you to the steps and considerations of the wizard mode generation API.

Using the wizard mode to generate data, the API is simple and easy to get started without writing any code, the API can be quickly generated by checking the configuration from the product interface. We recommend that users who do not have high requirements for the functions of the API or have little code development experience use the wizard.

**Note:** Before you configure the API, configure the data source in the **Data integration** \> **Data Source** page of the dataworks console.

## Configure the API basic information {#section_qdt_jzh_r2b .section}

1.  Navigate to the **API Service list** \> **Generate API**.
2.  Click **Wizard Mode**to fill in the API basics.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16407/15368068848791_en-US.png)

    Note the settings for the API grouping during configuration. An API group includes a collection of APIs that are used for a specific scenario. It is the minimum management unit in API Gateway. In the Alibaba Cloud API Market, each API group corresponds to a specific API product.

    **Note:** The set up example for API grouping is as follows:

    For example, you would like to configure an API product for weather inquiry, weather search API by city name weather search API, scenic spot name search weather API and zip search weather API three kinds of APIS, then you can create an API group called a weather query, and put the above three APIs in this group. The API is shown as a weather query product when published to the market.

    Of course, if your generated API is used in your own app, you can use grouping as a classification.

    Currently, the build API only supports HTTP protocol, GET request mode, and JSON return type.

3.  After providing the API basic information, click **Next** to go to the API parameter configuration page.

## Configure API parameters {#section_c1n_g13_r2b .section}

1.  Navigate to the **Data source type** \> **Data source name** \> **Table** and select the tables that you want to configure.

    **Note:** You need to configure the data source in advance in the data set, and the data table drop-down box supports the table name search.

2.  Second, specify request and response parameters.

    When a data table has been selected, all fields of the table are displayed on the left. Select the fields to be used as request parameters and response parameters, then add them to the corresponding parameter list.

3.  Finally, edit and complete parameter information.

    Click **Edit** in the upper-right corner of the request and return parameter lists to enter the parameter information Edit page, sets the name of the parameter, sample value, default, mandatory, fuzzy match \(only string type is supported\) settings\) and the description. The optional and description fields are required.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16407/15368068848794_en-US.png)


You need to pay attention to the settings that return result paging during the configuration process.

-   If you do not enable the **response pagination**, the API outputs up to 500 records by default.
-   If the return result may exceed 500, turn on the **response pagination**function.

The following public parameters are available only when the response pagination feature is enabled:

-   Common request parameters
    -   pageNum: the current page number.
    -   Pagesize: The page size, that is, the number of records per page.
-   Common response parameters
    -   pageNum: the current page number.
    -   Pagesize: The page size, that is, the number of records per page.
    -   totalNum: the total number of records.

**Note:** 

-   The request parameter only supports the equivalent query, and the return parameter only supports the output of the field value as is.
-   As far as possible, set an indexed field to a request parameter.
-   You are allowed to specify no request parameters for an API. In that case, the pagination feature must be enabled.
-   To make it easy for API callers to understand the details of an API, we recommend that you specify the sample value, default value, and description parameters of the API.
-   Click on the configured API to view a list of the APIs that have been generated in the current table, avoid generating the same API.

When the configuration of the API parameters is complete, click **Next** to enter the API testing section.

## API Testing {#section_d5j_nb3_r2b .section}

After completing configuration of API parameters, you can start the API test.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16407/15368068848797_en-US.png)

Set parameters and click **Start Test** to send the API request online. The API request details and response are displayed on the right. If the test fails, read the error message carefully and make the appropriate adjustments to test your API again.

You need to note the settings for the normal return example during the configuration process. When testing an API, the system automatically generates exception examples and error codes. However, normal response examples are not automatically generated. After the test succeeds, you need to click **Save as Normal Response Sample** to save the current test result as the normal response sample. If sensitive data is included in the response, you can manually edit it.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16407/15368068848799_en-US.png)

**Note:** 

-   Normal response examples provide an important reference value for the API callers. Specify an example if possible.
-   The API calling delay is the delay of the current API request, which is used to evaluate the API performance. If the latency is too high, you may consider optimizing your database.

After completing the API test, click **Finish**. The data API is successfully created.

## API details viewing {#section_xp4_mc3_r2b .section}

Back on the API service list page, click **details** in the Action column to view the details of the API. This page displays detailed information about an API from the view of a caller.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16407/15368068858800_en-US.png)
