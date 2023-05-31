# ImageUpload
asp.net Image Upload 
************************************************_____________***************


if (FileUpload3.HasFile)
                        {
                            string fileName = FileUpload3.PostedFile.FileName;
                            string fileExt = System.IO.Path.GetExtension(FileUpload3.FileName);
                            decimal size = Math.Round(((decimal)FileUpload3.PostedFile.ContentLength / (decimal)1024), 2);
                            if (FileUpload3.PostedFile.ContentLength <= 2048000)
                            {
                                if (fileExt.ToLower() == ".pdf")
                                {
                                    FileUpload3.PostedFile.SaveAs(Server.MapPath("/productpic/" + n1 + fileName));
                                    fileName_n3 = "/productpic/" + n1 + fileName;
                                }
                                else
                                {
                                    ScriptManager.RegisterClientScriptBlock(this, this.GetType(), "alertMessage", "alert('Please Upload Valid File')", true);
                                    return;
                                }
                            }
                            else
                            {
                                ScriptManager.RegisterClientScriptBlock(this, this.GetType(), "alertMessage", "alert('File size must not exceed 1 MB')", true);
                                return;
                            }
                        }
                        else
                        {
                            ScriptManager.RegisterClientScriptBlock(this, this.GetType(), "alertMessage", "alert('Please Upload File')", true);
                            return;
                        }
                       
