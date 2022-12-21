# Send-Email-In-Java
Send Email in Java

https://mkyong.com/java/javamail-api-sending-email-via-gmail-smtp-example/

Using Multipart file and Multiple Files

https://www.tutorialspoint.com/javamail_api/javamail_api_send_email_with_attachment.htm

https://stackoverflow.com/questions/49917576/email-sending-with-multiple-attachments-using-multipartfile

List<MultipartFile> attachments = /* this will be input for multiple files */
    Multipart multipart = new MimeMultipart();
    MimeBodyPart mimeBodyPart = new MimeBodyPart();
    mimeBodyPart.setContent(/* email content */, "text/html");
    multipart.addBodyPart(mimeBodyPart);
    for(int i = 0 ; i < attachments.size() ; i++) {
        mimeBodyPart = new MimeBodyPart();
        DataSource source = new ByteArrayDataSource(attachments.get(i).getBytes(), attachments.get(i).getContentType());
        mimeBodyPart.setDataHandler(new DataHandler(source));
        mimeBodyPart.setFileName(attachments.get(i).getOriginalFilename());
        multipart.addBodyPart(mimeBodyPart);
    }

    email.setContent(multipart);





