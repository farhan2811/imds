<script type="text/javascript">
	import Sidebar from '../../../../components/sidebar.svelte'
	import Navbar from '../../../../components/navbar.svelte'
	import { onMount } from 'svelte';
	import {fly, scale} from 'svelte/transition'
	let tab_state = 1;
</script>

<div id="after-login-layout">
	<Navbar/>
	<div class="flex">
		<Sidebar statusPointer="KelolaPerum" pagePointer="admin"/>
		<div class="w-80 content">
			<div class="flex flex-direction-col flex-gap-large" in:fly={{ y: -20, duration: 600 }}>
				<div class="flex flex-between-horizontal flex-center-vertical w-100">
					<div class="flex  flex-direction-col flex-between-horizontal flex-gap-semi-small w-100">
						<div class="title-content">Detail Perumahan</div>
						<div class="flex flex-gap-regular flex-center-vertical">
							<div class="text-breadcrumb">Kelola Perum</div>
							<img src="/images/icons/Arrow_Right.svg">
							<div class="text-breadcrumb-active">Detail</div>
						</div>
					</div>
					<div class="flex flex-gap-regular">
						<a href="/super-admin/nup/edit-nup" class="no-decor"><button class="btn-fill-warning flex flex-center-vertical flex-gap-small"><img src="/images/icons/Edit_White.svg"> <span>Edit</span></button></a>
						<a href="/super-admin/nup/detail-nup" class="no-decor"><button class="btn-fill-danger flex flex-center-vertical flex-gap-small"><img src="/images/icons/Trash_White.svg"> <span>Hapus</span></button></a>
					</div>
				</div>
				<div class="card w-100 flex flex-gap-semi-large">
					<div class="w-40">
						<div class="w-100 h-100 img-perum"></div>
					</div>
					<div class="w-60 flex flex-direction-col flex-gap-large">
						<div class="flex flex-gap-regular">
							<div class="w-50 flex flex-direction-col flex-gap-regular">
								<div class="flex flex-direction-col">
									<div class="caption-card-detail">Nama Perusahaan</div>
									<div class="content-card-detail">Griya Panorama Cimanggung</div>
								</div>
								<div class="flex flex-direction-col">
									<div class="caption-card-detail">Alamat Perumahan</div>
									<div class="content-card-detail">Jl. Perumahan Kemerdekaan No. 42</div>
								</div>
								<div class="flex w-100">
									<div class="flex flex-direction-col w-50">
										<div class="caption-card-detail">Provinsi</div>
										<div class="content-card-detail">Jawa Timur</div>
									</div>
									<div class="flex flex-direction-col">
										<div class="caption-card-detail">Kode Pos</div>
										<div class="content-card-detail">13210</div>
									</div>
								</div>
							</div>
							<div class="w-50 flex flex-direction-col flex-gap-regular">
								<div class="flex flex-direction-col">
									<div class="caption-card-detail">Singkatan Perumahan</div>
									<div class="content-card-detail">GPC</div>
								</div>
								<div class="flex flex-direction-col">
									<div class="caption-card-detail">Telepon</div>
									<div class="content-card-detail">08XXXXXXXXX</div>
								</div>
								<div class="flex w-100">
									<div class="flex flex-direction-col w-50">
										<div class="caption-card-detail">Fax</div>
										<div class="content-card-detail">202-XXX-XXX</div>
									</div>
									<div class="flex flex-direction-col">
										<div class="caption-card-detail">Site Plan</div>
										<div class="flex flex-center-vertical flex-gap-semi-small">
											<a href="#" class="no-decor link-detail-akun">Lihat Site Plan</a>
											<img src="/images/icons/External_Link.svg">
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
				<div class="flex flex-direction-col flex-gap-regular">
					<div class="flex flex-direction-col flex-gap-small">
						<div class="flex flex-gap-regular">
							<span class="{tab_state == 1 ? 'active-notif-button' : 'unactive-notif-button'}" on:click={() => {tab_state = 1}}>Daftar Unit</span>
							<span class="{tab_state == 2 ? 'active-notif-button' : 'unactive-notif-button'}" on:click={() => {tab_state = 2}}>Daftar Blok</span>
						</div>
					</div>
				</div>
				{#if tab_state == 1}
				<div class="flex flex-direction-col flex-gap-regular" in:fly={{ y: -20, duration: 600 }}>
					<div class="flex">
						<div class="flex flex-gap-semi-large w-60">
							<input type="text" placeholder="Cari Kode" class="input-col-2 w-25">
							<input type="text" placeholder="Blok Rumah" class="input-col-2 w-25">
							<select class="select-col-3 w-20">
								<option selected disabled>Tipe</option>
								<option>Serpong</option>
							</select>
						</div>
						<div class="w-40 flex flex-end-horizontal">
							<a href="/super-admin/kelola-perum/detail-perumahan/tambah-unit" class="no-decor"><button class="btn-fill flex flex-center-vertical flex-gap-small"><img src="/images/icons/Add_Plus.svg"> <span>Tambah Unit</span></button></a>
						</div>
					</div>
					<div class="scroll-x flex flex-direction-col flex-gap-regular">
						<div class="card-head w-content-7 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-25 border-separate">
									<div class="text-drop-card">Kode Unit</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
									<div class="text-drop-card">Blok</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
									<div class="text-drop-card">No</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 border-separate">
									<div class="text-drop-card">Lantai</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 border-separate">
									<div class="text-drop-card">Tipe</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Harga Unit</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Pricelist</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-direction-col flex-center-horizontal flex-center-vertical w-80 border-separate-2">
									<div class="flex w-100 flex-center-horizontal border-bottom-seperate">
										<div class="text-drop-card padding-spec-nup-1">Waktu Pembangunan</div>
									</div>
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1 ">Mulai</div>
										</div>
										<div class="flex flex-center-horizontal w-31 border-separate-2">
											<div class="text-drop-card padding-spec-nup-1">Target</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">Sisa</div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 border-separate">
									<div class="text-drop-card">Progress Pembangunan</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Progress Teknis</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Progress Legal</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Progress Marketing</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
									<div class="text-drop-card">Status</div>
									<img src="/images/icons/Arrow.svg">
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15 border-non-separate">
									<div class="text-drop-card">Aksi</div>
									<img src="/images/icons/Arrow.svg">
								</div>
							</div>
						</div>
						<div class="card-head w-content-7 height-fit">
							<div class="flex">
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">GPCAO02</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">AO</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">2</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-20 no-border-table">
									<div class="text-drop-card">1</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
									<div class="text-drop-card">36/104</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">Rp. 5.000.000</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-drop-card">V.2018.04.14</div>
								</div>
								<div class="flex flex-direction-col flex-center-horizontal flex-center-vertical w-80 border-separate-1">
									<div class="flex w-100 flex-center-horizontal">
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">1 Feb 23</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1">1 Feb 23</div>
										</div>
										<div class="flex flex-center-horizontal w-31">
											<div class="text-drop-card padding-spec-nup-1 ">4 Bulan</div>
										</div>
									</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-approve">100%</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-approve">100%</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-approve">100%</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-60 no-border-table">
									<div class="text-drop-card">SPPKR</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
									<div class="text-approve">Terjual</div>
								</div>
								<div class="flex flex-gap-small flex-center-vertical w-15 border-non-separate">
										<a href="/super-admin/kelola-perum/detail-perumahan/edit-unit" class="no-decor"><img src="/images/icons/Edit.svg"></a>
										<img src="/images/icons/Delete.svg">
									</div>
							</div>
						</div>
					</div>
					<div class="card w-100 height-fit">
						<div class="flex flex-between-horizontal">
							<div class="flex flex-gap-regular flex-center-vertical">
								<div class="text-display-sort">Menampilkan</div>
								<select class="select-sort">
									<option>10</option>
								</select>
								<div class="text-display-sort">dari <span class="bold-number">28</span> data Rekap Data</div>
							</div>
							<div class="flex flex-gap-regular flex-center-vertical">
								<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><img src="/images/icons/Arrow_Left.svg"></div>
								<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><div class="text-display-sort bold-number">1</div></div>
								<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><img src="/images/icons/Arrow_Right.svg"></div>
							</div>
						</div>
					</div>
				</div>
				{:else if tab_state == 2}
				<div class="w-60">
					<div class="flex flex-direction-col flex-gap-regular" in:fly={{ y: -20, duration: 600 }}>
						<div class="flex">
							<div class="flex flex-gap-semi-large w-70">
								<input type="text" placeholder="Cari Blok" class="input-col-2 w-50">
							</div>
							<div class="w-40 flex flex-end-horizontal">
								<a href="/super-admin/kelola-perum/detail-perumahan/tambah-blok" class="no-decor"><button class="btn-fill flex flex-center-vertical flex-gap-small"><img src="/images/icons/Add_Plus.svg"> <span>Tambah Blok</span></button></a>
							</div>
						</div>
						<div class="scroll-x flex flex-direction-col flex-gap-regular">
							<div class="card-head w-100 height-fit">
								<div class="flex">
									<div class="flex flex-gap-small flex-center-vertical w-15 border-separate">
										<div class="text-drop-card">Blok</div>
										<img src="/images/icons/Arrow.svg">
									</div>
									<div class="flex flex-gap-small flex-center-vertical w-40 border-separate">
										<div class="text-drop-card">Alamat</div>
										<img src="/images/icons/Arrow.svg">
									</div>
									<div class="flex flex-gap-small flex-center-vertical w-25 border-separate">
										<div class="text-drop-card">Jumlah Unit</div>
										<img src="/images/icons/Arrow.svg">
									</div>
									<div class="flex flex-gap-small flex-center-vertical w-10 border-non-separate">
										<div class="text-drop-card">Aksi</div>
										<img src="/images/icons/Arrow.svg">
									</div>
								</div>
							</div>
							<div class="card-head w-100 height-fit">
								<div class="flex">
									<div class="flex flex-gap-small flex-center-vertical w-15 no-border-table">
										<div class="text-drop-card">AA</div>
									</div>
									<div class="flex flex-gap-small flex-center-vertical w-40 no-border-table">
										<div class="text-drop-card">Jl. Perintis Kemerdakaan No. 42, Blok AA</div>
									</div>
									<div class="flex flex-gap-small flex-center-vertical w-25 no-border-table">
										<div class="text-drop-card">10</div>
									</div>
									<div class="flex flex-gap-small flex-center-vertical w-10 border-non-separate">
											<a href="/super-admin/kelola-perum/detail-perumahan/edit-blok" class="no-decor"><img src="/images/icons/Edit.svg"></a>
											<img src="/images/icons/Delete.svg">
										</div>
								</div>
							</div>
						</div>
						<div class="card w-100 height-fit">
							<div class="flex flex-between-horizontal">
								<div class="flex flex-gap-regular flex-center-vertical">
									<div class="text-display-sort">Menampilkan</div>
									<select class="select-sort">
										<option>10</option>
									</select>
									<div class="text-display-sort">dari <span class="bold-number">28</span> data Rekap Data</div>
								</div>
								<div class="flex flex-gap-regular flex-center-vertical">
									<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><img src="/images/icons/Arrow_Left.svg"></div>
									<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><div class="text-display-sort bold-number">1</div></div>
									<div class="flex flex-center-vertical flex-center-horizontal border-pagination"><img src="/images/icons/Arrow_Right.svg"></div>
								</div>
							</div>
						</div>
					</div>
				</div>
				{/if}
			</div>
		</div>
	</div>
</div>