# multipart_parser

#简单的multifrom-data解析

#例子：

#define BODY                                                                \
    "--" BOUNDARY "\r\n"                                                    \
    "Content-Disposition: form-data; name=\"username\"\r\n\r\n"                 \
     "yinpinghua\r\n"                                                      \
     "--" BOUNDARY "\r\n"													\
     "Content-Disposition: form-data; name=\"password\"\r\n\r\n"               \
     "xw123456\r\n"                                                        \
    "--" BOUNDARY "--\r\n"                                                \

	multipart_parser parser(BOUNDARY);
	if (strlen(BODY) == parser.parser_data(BODY, strlen(BODY))) {
		std::cout << "nice" << std::endl;
	}

    parser.get_multipart_data();
    
