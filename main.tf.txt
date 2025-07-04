provider "aws" {
  region = "ap-south-1"
}

resource "aws_instance" "my_ec2" {
  ami           = "ami-03f4878755434977f"
  instance_type = "t2.micro"
  tags = {
    Name = "TerraformEC2"
  }
}

resource "aws_s3_bucket" "my_bucket" {
  bucket = "thrishika-demo-bucket-12345"   # must be globally unique
  acl    = "private"

  tags = {
    Name        = "TerraformS3"
    Environment = "Dev"
  }
}
