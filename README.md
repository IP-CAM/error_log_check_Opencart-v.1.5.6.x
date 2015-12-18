# error log check OpenCart

Simple module which checks the error file (error.txt) when its size exceeds 1MB and notify you.

View vqmod file 

or

add thist code in /admin/view/template/common/header.tpl after all code

<style type="text/css">
			#content {
			padding-top: 20px!important;
			}
			.warning {
			position: absolute!important;
			margin-top: 4px;
			margin-left: 30px;
			}
			</style>
			
	<?php
	
	$filename = $file = DIR_LOGS . $this->config->get('config_error_filename');
	
	if (filesize($filename) > 1000000) {
		echo '<div class="warning" >';
		echo $filename . ': ' . filesize($filename) ;
		echo ' bytes';
		echo '<a href="';
		echo $this->data['clear'] = $this->url->link('tool/error_log/clear', 'token=' . $this->session->data['token'], 'SSL');
		echo '" > CLEAR</a>';
		echo '</div>';
	} else {
	}
	
	?>
