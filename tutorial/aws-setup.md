# Set up a new AWS


# Mount disk

cd $HOME
mkdir storage
mkfs -t ext4 /dev/xvdb
sudo mount /dev/xvdb ./storage
