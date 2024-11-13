# 233769-vp-lab-6
using System;
using System.Collections;
using System.Windows.Forms;

namespace ListArrayListApp
{
    public partial class Form1 : Form
    {
        private ArrayList items;

        public Form1()
        {
            InitializeComponent();
            items = new ArrayList();
        }

        private void btnAdd_Click(object sender, EventArgs e)
        {
            string newItem = txtItem.Text.Trim();
            if (!string.IsNullOrEmpty(newItem))
            {
                items.Add(newItem);
                txtItem.Clear();
                MessageBox.Show("Item added!");
            }
            else
            {
                MessageBox.Show("Please enter a valid item.");
            }
        }

        private void btnRemove_Click(object sender, EventArgs e)
        {
            string itemToRemove = txtItem.Text.Trim();
            if (items.Contains(itemToRemove))
            {
                items.Remove(itemToRemove);
                txtItem.Clear();
                MessageBox.Show("Item removed!");
            }
            else
            {
                MessageBox.Show("Item not found.");
            }
        }

        private void btnDisplay_Click(object sender, EventArgs e)
        {
            lstItems.Items.Clear();
            foreach (var item in items)
            {
                lstItems.Items.Add(item);
            }
        }
    }
}
